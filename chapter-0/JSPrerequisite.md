## Minimun Javascript Syntax required to learn React

1. **let and const**

``

    const name = "Tony Stark" // define a value as const if you don't want it to change

    let age = 40 // define a value as let if you expect it to change

    // Both let and const are block scoped


``

2. **Template Literals**

``

    const name = "Peter Parker"

    const welcomeMsg = `Welcome to Avengers, ${name}`

    console.log(welcomeMsg)

    function getName(){ return "Peter Parker"}

    const welcomeMsgFunc = `Welcome to Avengers, ${getName()}`

    console.log(welcomeMsgFunc)

``

3. **Shorthand Property**

``

    const realName = "Tony Stark"
    const superheroName = "Iron Man"

    const member = {
        realName,
        superheroName
    }

    //if the key name and value variable name is same then you can just specify the key name

``

4. **Arrow functions**

``

    function getTeamName() {
        return "Avengers"
    }

    const getTeamName = () => "Avengers"

    const greetMember = name => `Welcome ${name}`

    let memberInfo;
    const setMemberInfo = (realName, superheroName) => {
        memberInfo = {
            realName,
            superheroName
        }
    } 

    const getMemberInfo = () => ({realName: "Tony Stark", superheroName: "Iron man"})

``

5. **Destructuring**

``

    const memberInfo = {
        realName: "Tony Stark",
        superheroName: "Iron man",
        team: "Avengers"
    }

    const { superheroName } = memberInfo;

    const members = ["Tony Stark", "Steve Rogers", "Bruce Banner", "Natasha Romanoff", "Clint Barton", "Thor"]

    const [a,b,,,c] = members;

    // a is "Tony Stark", b is "Steve Rogers" & c is "Clint Barton"

``

6. **Parameter defaults**

``

    const setTeam = (teamName = "Avengers") => {
        console.log(teamName)
    }

    setTeam()

    const setMemberInfo = ({ realName = "Tony Stark", superheroName = "Iron Man", team = "Avengers"} = {}) => {
        console.log(`Real name is ${realName}, Superhero name is ${superheroName} and the team is ${team}`)
    }

    setMemberInfo({realName: "Bruce Banner", superheroName: "Hulk"})
    setMemberInfo()

``

7. **Spread and Rest**

``

    const avengers = ["Tony Stark", "Steve Rogers", "Bruce Banner", "Natasha Romanoff", "Clint Barton", "Thor"]

    const newAvengers = [...avengers, "Vision", "Wanda", "Falcon"]

    const memberInfo = {
        realName: "Rocket",
        superheroName: "Rocket",
        team: "Guardians"
    }

    const newMemberInfo = {...memberInfo, team:"Avengers"}

``

8. **Module Exports**

``

    // Members.js
    export const name = "Steve Rogers"

    import {name} from './Members.js'

    // Teams.js
    const Team = "Avengers"

    export default Team

    import Team from './Teams.js'

``

9. **Ternary conditional operator**

``

    let name = "Clint Barton"

    const superheroName = name === "Clint Barton" ? "Hawkeye" : null

    name = "Tony Stark"

    const superheroName2 = name === "Clint Barton" ? "Hawkeye" : name === "Tony Stark" ? "Iron Man" : null

``

10. **Array methods**

    - map

        ``

            const members = ["Tony Stark", "Steve Rogers", "Bruce Banner", "Natasha Romanoff", "Clint Barton", "Thor"]

            const memberWithTeam = members.map((member, index) => {
                return {
                    id: index + 1,
                    name: member,
                    team: "Avengers"
                }
            })

            console.log(memberWithTeam)

        ``

    - filter

        ``

            const resultMembers =  memberWithTeam.filter((member) => {
                if(member.id > 3)
                    return true
                return false
            })

            console.log(resultMembers)
	    
        ``

    - reduce
    - find
    - some
    - every
    - includes

11. **Short-circuit operator**

``

    const avengers = ["Tony Stark", "Steve Rogers", "Bruce Banner", "Natasha Romanoff", "Clint Barton", "Thor"]

    console.log(avengers && avengers.length !== 0 && "Avengers are present")
    
``

12. **Optional chaining**

``

    const memberInfo = {
        realName: "Rocket",
        superheroName: "Rocket",
        team: "Guardians"
    }

    console.log(memberInfo.teamName?.name)

    console.log(memberInfo.teamName.name)
    
``

13. **Promises and Async/Await**

``

    const fetchData = async (url) => {
	    const result = await window.fetch(url)
	    const data = await result.json()
	    console.log(data)
    }

    const url = "https://jsonplaceholder.typicode.com/users/"
    fetchData(url)
    
``
