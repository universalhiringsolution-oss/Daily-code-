# Daily-code-



















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


