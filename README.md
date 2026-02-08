<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name:VEMBARASI.A.R</h3>
<h3>Register Number:212224220120</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>
<h3>PROGRAM :</h3>
<h3>
import random
rooms = ["Room 1", "Room 2"]
patients = {
    "Room 1": random.uniform(97.0, 102.0),
    "Room 2": random.uniform(97.0, 102.0)
}

FEVER_TEMP = 98.5

agent_location = "Room 1"
performance = 0
def sense_temperature(room):
    return patients[room]

def prescribe_medicine(room):
    global performance
    print(f" Prescribing medicine in {room}")
    performance += 10   # reward for treatment

def move_agent(current_room):
    global performance
    new_room = "Room 2" if current_room == "Room 1" else "Room 1"
    print(f" Moving from {current_room} to {new_room}")
    performance -= 2    # movement cost
    return new_room

print("Initial Patient Temperatures:")
for room, temp in patients.items():
    print(f"{room}: {temp:.2f}°F")

print("\nAgent starting in", agent_location)

for _ in range(2):
    temp = sense_temperature(agent_location)
    print(f"\nAgent in {agent_location}")
    print(f" Sensed temperature: {temp:.2f}°F")

    if temp > FEVER_TEMP:
        prescribe_medicine(agent_location)
    else:
        print(" Patient is healthy")

    agent_location = move_agent(agent_location)
print("\nFinal Performance Score:", performance)

</h3>
<h3>OUTPUT : </h3>
<img width="544" height="391" alt="image" src="https://github.com/user-attachments/assets/df838ccb-6bdd-4fdb-998e-6c2152c9c23c" />

<h3>RESULT :</h3>
<p>Thus the given AI problem was developed an AI agent and has been executed successfully.</p>
