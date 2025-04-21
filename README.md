# RESUMEBUILDER
Build the resume
// App.jsx import React, { useState } from "react"; import { saveAs } from "file-saver";

export default function App() { const [formData, setFormData] = useState({ name: "", email: "", phone: "", summary: "", skills: "" });

const handleChange = (e) => { setFormData({ ...formData, [e.target.name]: e.target.value }); };

const handleDownload = () => { const resumeContent = Name: ${formData.name}\nEmail: ${formData.email}\nPhone: ${formData.phone}\n\nSummary:\n${formData.summary}\n\nSkills:\n${formData.skills}; const blob = new Blob([resumeContent], { type: "text/plain;charset=utf-8" }); saveAs(blob, "resume.txt"); };

return ( <div className="min-h-screen p-4 bg-gray-100"> <h1 className="text-2xl font-bold mb-4 text-center">Resume Builder</h1> <div className="grid md:grid-cols-2 gap-4"> <div className="bg-white p-4 rounded-2xl shadow"> <input
type="text"
name="name"
placeholder="Name"
value={formData.name}
onChange={handleChange}
className="w-full mb-2 p-2 border rounded"
/> <input
type="email"
name="email"
placeholder="Email"
value={formData.email}
onChange={handleChange}
className="w-full mb-2 p-2 border rounded"
/> <input
type="text"
name="phone"
placeholder="Phone"
value={formData.phone}
onChange={handleChange}
className="w-full mb-2 p-2 border rounded"
/> <textarea
name="summary"
placeholder="Professional Summary"
value={formData.summary}
onChange={handleChange}
className="w-full mb-2 p-2 border rounded"
/> <textarea
name="skills"
placeholder="Skills (comma separated)"
value={formData.skills}
onChange={handleChange}
className="w-full mb-2 p-2 border rounded"
/> <button
onClick={handleDownload}
className="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600"
> Download Resume </button> </div>

<div className="bg-white p-4 rounded-2xl shadow">
      <h2 className="text-xl font-semibold mb-2">Preview</h2>
      <p><strong>Name:</strong> {formData.name}</p>
      <p><strong>Email:</strong> {formData.email}</p>
      <p><strong>Phone:</strong> {formData.phone}</p>
      <p><strong>Summary:</strong><br /> {formData.summary}</p>
      <p><strong>Skills:</strong><br /> {formData.skills}</p>
    </div>
  </div>
</div>

); }

