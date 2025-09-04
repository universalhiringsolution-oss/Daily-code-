# Daily-code-













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


