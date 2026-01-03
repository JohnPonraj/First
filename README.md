import React, { useState } from "react";

function App() { const [name, setName] = useState(""); const [students, setStudents] = useState([]);

const addStudent = () => { if (name === "") return; setStudents([...students, name]); setName(""); };

return ( <div style={{ padding: "20px" }}> <h2>Student Management App</h2>

<input
    type="text"
    placeholder="Enter student name"
    value={name}
    onChange={(e) => setName(e.target.value)}
  />

  <button onClick={addStudent} style={{ marginLeft: "10px" }}>
    Add
  </button>

  <h3>Student List</h3>
  <ul>
    {students.map((student, index) => (
      <li key={index}>{student}</li>
    ))}
  </ul>
</div>

); }

export default App;
