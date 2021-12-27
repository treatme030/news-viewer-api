<img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"><img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"><img src="https://img.shields.io/badge/html-E34F26?style=for-the-badge&logo=html5&logoColor=white"><img src="https://img.shields.io/badge/styled components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white"><img src="https://img.shields.io/badge/React Router-CA4245?style=for-the-badge&logo=React Router&logoColor=black">


# react-news-viewer-api
 * usePromise hook을 만들어 대기중, 성공, 실패에 대한 상태 관리
 ```javascript
 import { useEffect, useState } from "react";

 export default function usePromise(promiseCreator, deps){
    const [loading, setLoading] = useState(false)
    const [resolved, setResolved] = useState(null)
    const [error, setError] = useState(null)

    useEffect(() => {
        const process = async () => {
            setLoading(true)
            try {
                const resolved = await promiseCreator()
                setResolved(resolved)
            }catch(e){
                setError(e)
            }
            setLoading(false)
        }
        process()
    }, deps)

    return [loading, resolved, error]
 }
 ```
  * 카테고리 검색 

![pnew](https://user-images.githubusercontent.com/74355328/147448724-657de293-dc6b-40c8-ad86-d9d091e0bef2.gif)
