To reproduce run `yarn && yarn build`

issue:
- `packageA` is `bs-dependency` of `root` package.
- `packageA` is using `subpackageB` as `bs-dependency`
- building `root` outputs invalid TS code for `packageA`
    ```
    import {Demo_myint as SubpackageB_Demo_myint} from './SubpackageB.gen';
    ```
   instead of 
    ```
    import {Demo_myint as SubpackageB_Demo_myint} from 'subpackageB/Demo.gen';
    ```
