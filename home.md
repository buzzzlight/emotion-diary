기초공사

1. 상태관리 세팅

   - 프로젝트 전반적으로 사용될 일기 데이터 State 관리 로직 작성하기

   ```
   <App/> 일기데이터 State
   <ReactRouter/>
   
   <Home/> 일기 리스트 -> 일기 데이터 리스트 state 필요
   <New/> 일기 생성 로직 -> 새로운 일기 데이터 추가하는 역할
   <Edit/> 일기 수정 로직
   <Diary/> 일기 하나의 데이터
   ```

2. 프로젝트 State Context 세팅하기

   - 일기 데이터 State를 공급할 Context를 생성하고 Provider로 공급하기

   ```js
   export const DiaryStateContext = React.createContext();
   export const DiaryDispatchContext = React.createContext();
   ```

   ```js
     return (
       <DiaryStateContext.Provider value={data}>
         <DiaryDispatchContext.Provider value={{ onCreate, onEdit, onRemove }}>
           // 페이지 라우팅
           <BrowserRouter>
             <div className="App">
               <Routes>
                 <Route path="/" element={<Home />} />
                 <Route path="/new" element={<New />} />
                 <Route path="/edit" element={<Edit />} />
                 <Route path="/diary/:id" element={<Diary />} />
               </Routes>
             </div>
           </BrowserRouter>
         </DiaryDispatchContext.Provider>
       </DiaryStateContext.Provider>
     );
   }
   ```

3. 프로젝트 Dispatch Context 세팅하기

   - 일기 데이터 State의 Dispatch 함수들을 공급할 Context를 생성하고 Provider로 공급하기





# Home

