# Daily-code-




**12-09-2025**




import { Routes, Route } from "react-router";
import Login from "./login";
import Info from "./info";
import NavBar from "./NavBar";
import Home from "./home";

export function App() {
    return (
        <>

<section>
            <NavBar />

</section>



            <Routes>
                <Route path='/' element={<Home />} />
                <Route path='/Login' element={<Login />} />
                <Route path='/Info' element={<Info />} />
            </Routes>


        </>
    )
}









**11-09-2025**


import { BrowserRouter, Routes, Route, Link } from "react-router";
export default function App() {

    return (

        <>
            <BrowserRouter>

                <Link to='/'>Home </Link>
                <Link to='/About'>About </Link>
                <Link to='/Contact'>Contact </Link>
                <Link to='/Info'>Info </Link>

                <Routes>
                    <Route path='/' element={<h1>Home</h1>} />
                    <Route path='/About' element={<h1>About</h1>} />
                    <Route path='/Contact' element={<h1>Contact</h1>} />
                    <Route path='/Info' element={<h1>Info</h1>} />
                </Routes>

            </BrowserRouter>

        </>



    )

}





**10-09-2025**






import College from "./college"
import { SubjectContext } from "./ContextData"
import { useState } from "react"


export default function App() {

    const [subject, setSubject] = useState('English')

    return (
        <>
            <h1 style={{ backgroundColor: 'yellow', padding: '100px', width: '1800px' }} > Context AP </h1>

            <SubjectContext.Provider value={subject}>
                <select Value={subject} onChange={(event) => setSubject(event.target.value)}>
                    <option value="English">English</option>
                    <option value="Maths">Maths</option>
                    <option value="Science">Science</option>
                    <option value="Geography">Geography</option>
                    <option value="Social Study">Social Study</option>
                    <option value="PCMB">PCMB</option>

                </select>
                <button onClick={() => setSubject('')}>Clear Subject </button>

                <College />

            </SubjectContext.Provider>
        </>
    )
}



// import ClassComponent from "./ClassComponent"


// export default function College() {
//     return (
//         <>
//             <h1 style={{ backgroundColor: 'orange', padding: '70px' }}> College Component 
//                   <ClassComponent />
//                  </h1>
          

//         </>
//     )
// }


// import Student from "./student";


// export default function ClassComponent() {
//     return (
//         <>
//             <h1 style={{ backgroundColor: 'Skyblue', padding: '40px' }}> ClassComponent Component 
//                 <Student />
//                  </h1>


//         </>
//     )
// }


// import Subject from "./Subject";


// export default function Student() {
//     return (

//         <>
//             <h1 style={{ backgroundColor: 'green', padding: '30px' }}> Student Component
//                 <Subject />
                
//             </h1>

//         </>
//     )
// }



// import { SubjectContext } from './ContextData';
// import { useContext } from 'react'

// export default function Subject() {
//     const subject = useContext(SubjectContext)
//     return (
//         <>
//             <h1 style={{ backgroundColor: 'red', padding: '30px' }}> Subject Component  </h1>


//                 <h2> Subject is : {subject}</h2>







//         </>
//     )
// }



// import { createContext } from "react";


// export const SubjectContext=createContext('Maths')
































**09-09-2025**




// UseToggle.jsx
import { useState } from 'react'


const useToggle = (defaultVal) => {
    const [value, setValue] = useState(defaultVal);

    function toggleValue(val) {
        if (typeof val != 'boolean') {
            console.log(val);  
            setValue(!value)
        } else {
            setValue(val)
        }
    }
    return [value, toggleValue]
}


export default useToggle;



// /////////////////////////////////////







import useToggle from "./UseToggle"


export default function App() {

    const [value, toggleValue] = useToggle(true);

    const [data,setData]=useToggle(true);


    return (
        <>

            <button onClick={toggleValue} >Toggle Heading </button>
            <button onClick={()=>toggleValue(false)} >Hide Heading </button>
            <button onClick={()=>toggleValue(true)} >Show Heading </button>


            {
                value ? <h1> Custom Hook in react</h1> : null
            }

<hr />

<h1> Second heading </h1>

            <button onClick={setData} >Toggle Heading </button>
            <button onClick={()=>setData(false)} >Hide Heading </button>
            <button onClick={()=>setData(true)} >Show Heading </button>

            {
                data ? <h1> Custom Hook in react</h1> : null
            }





        </>
    )

}

























**08-09-2025**

import { Fragment } from 'react'


export default function App() {
    return (
        // <Fragment>

        //     <h1> Fragment in React JS </h1>
        //     <h1> Fragment in React JS </h1>


        // </Fragment>

        <div>
            <Data />
            <Data />
            <Data />
            <Data />
            <Data />
        </div>




    )
}


function Data() {
    return (

        // <Fragment>

        //     <h1> Fragment in React JS </h1>
        //     <h1> Fragment in React JS </h1>


        // </Fragment>

        <div>

<span> Hello <b>Submit </b></span>

        </div>

    )
}










**05-09-2025**



import { useId } from 'react'

export default function App() {

    return (
        <>

            <UserForm />


        </>
    )

}


function UserForm() {

    const user = useId();


    return (
        <>
            <form action="">
                <label htmlFor={user + "name"}> Enter User Name</label>
                <input id={user + "name"} type="text" placeholder='enter name' />

            </form>
            <br />
            <form action="">
                <label htmlFor={user + "Password"}> Enter User Password</label>
                <input id={user + "Password"} type="text" placeholder='enter password' />

            </form>

            <br />
            <form action="">
                <label htmlFor={user + "Password"}> Enter User Skills</label>
                <input id={user + "Password"} type="text" placeholder='enter skill' />

            </form>
            <br />
            <form action="">

                <input id={user + "terms"} type="checkbox" placeholder='enter Terms' />
                <label htmlFor={user + "terms"}> Enter User terms </label>

            </form>

            <button> Submit </button>
            <hr />

            <form action="">
                <label htmlFor={user + "name"}> Enter User Name</label>
                <input id={user + "name"} type="text" placeholder='enter name' />

            </form>
            <br />
            <form action="">
                <label htmlFor={user + "Password"}> Enter User Password</label>
                <input id={user + "Password"} type="text" placeholder='enter password' />

            </form>

            <br />
            <form action="">
                <label htmlFor={user + "Password"}> Enter User Skills</label>
                <input id={user + "Password"} type="text" placeholder='enter skill' />

            </form>
            <br />
            <form action="">

                <input id={user + "terms"} type="checkbox" placeholder='enter Terms' />
                <label htmlFor={user + "terms"}> Enter User terms </label>

            </form>

            <button> Submit </button>
            <hr />

        </>
    )

}













**06-09-2025**


import { useActionState } from 'react'



export default function App() {

    const handleSubmit = async (previousData, formData) => {
        let name = formData.get('name');
        let password = formData.get('password');

        console.log('handleSubmit called', name, password)
        await new Promise(res => setTimeout(res, 2000))
        if (name && password) {
            return { message: 'data submitted ', name, password };
        } else {
            return { error: 'failed to submit. enter proper data ' };
        }
    }
    const [data, action, pending] = useActionState(handleSubmit, undefined)
    console.log(data);

    return (

        <>

            <h1> useActionState hook in React Js </h1>
            <form action={action}>
                <input defaultValue={data?.name} type="text" placeholder='enter Name' name='name' />
                <br /> <br />

                <input defaultValue={data?.password} type="Password" placeholder='enter password' name='password' />
                <br /> <br />
                <button disabled={pending}> Submit Button </button>
                <br />

                {
                    data?.error && <span style={{ color: 'red' }}>{data?.error}</span>
                }

                {
                    data?.message && <span style={{ color: "green" }}>{data?.message}</span>
                }

                <h3> Name: {data?.name} </h3>
                <h3>Password: {data?.password}</h3>


            </form>


        </>
    )

}

















**05-09-2025**



import { useState } from "react";

export default function App() {
    const [data, setData] = useState([
        'anil', 'sam', 'peter'
    ])

    const [dataDetails, setDataDetails] = useState([
        {
            name: 'anil', age: '12'
        },
        {
            name: 'Bruce', age: '22'
        },
        {
            name: 'Carter', age: '19'
        }
    ])

    const handleUser = (name) => {

        data[data.length - 1] = name;
        console.log(data);
        setData([...data])

    }


    const handleAge = (age) => {

        dataDetails[dataDetails.length - 1].age = age;
        console.log(dataDetails);
        setDataDetails([...dataDetails])

    }


    return (

        <>

            <h1>Updating Array in State </h1>
            <input type="text" placeholder='enter last name' onChange={(e) => handleUser(e.target.value)} />
            {
                data.map((item, index) => (
                    <h3 key={index}>{item}</h3>
                ))

            }

            <hr />

            <input type="text" placeholder='enter last user age' onChange={(e) => handleAge(e.target.value)} />

            {
                dataDetails.map((item) => (
                    <h4>{item.name},{item.age}</h4>
                ))
            }



        </>

    )


}



**04-09-2025**


import { useState } from 'react'


export default function App() {


    const [data, setData] = useState({
        name: 'Anil',
        address: {
            city: 'delhi',
            country: 'india'
        }
    })


    const handleName = (val) => {
        data.name = val
        console.log(data);


        setData({ ...data })
    }

    const handlecity = (city) => {
        data.address.city = city;
        console.log(data);
        setData({ ...data, address: { ...data.address,city } })
    }
    return (

        <>

            <h1>Update objects in state </h1>

            <button onClick={handleName} >Update Name</button>

            <input type="text" placeholder='update name' onChange={(event) => handleName(event.target.value)} />
            <input type="text" placeholder='update City' onChange={(event) => handlecity(event.target.value)} />
            <h2>{data.name}</h2>
            <h2>{data.address.city}</h2>
            <h2>{data.address.country}</h2>

        </>

    )
}





















**04-09-2025**
import { useState } from 'react'
import AddUser from "./AddUser";
import Display from "./DisplayUser";


function App() {
    const [user, setUser] = useState('')

    return (

        <>
            <h1> Lift Up Data </h1>

            < AddUser setUser={setUser}/>
            < Display user={user} />

        </>

    )
}





export default App;




function AddUser({setUser}) {


    return (
        <>
            <h1> Add user</h1>
            <input type="text" onChange={(event)=>setUser(event.target.value)} placeholder='add user name' />
            <br />
            <button> Submit </button>
            <hr />
        </>
    )
}

export default AddUser;



function DisplayUser({ user }) {
    return (
        <>
            <h1> {user}</h1>
        </>
    )
}

export default DisplayUser







**03-09-2025**

import { useState } from 'react'


function App() {

    const [users, setUsers] = useState([])
    const [user, setUser] = useState('');

    const handleAddUsers = () => {
        setUsers([...users, user])
    }

    const Total = users.length;
    const Last = users[users.length - 1];
    const Uniques = [...new Set(users)].length


    return (

        <>
            <h2> Total User : {Total}</h2>
            <h2> Last User :{Last} </h2>
            <h2> Uniques User :{Uniques} </h2>


            <input type="text" onChange={(event) => setUser(event.target.value)} placeholder='add new user' />
            <button onClick={handleAddUsers}> Add User </button>
            {
                users.map((item, index) => (
                    <h4 Key={index}> {item}</h4>
                ))
            }

        </>

    )
}





export default App;


