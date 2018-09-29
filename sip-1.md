SIP-1

Simple Summary

A standard interface for match info.

Abstract

The following standard allows for the implementation of a standard API for match score within smart contracts. This standard provides basic functionality to fatch match score.

Specifcation

Methods


match Info

return match info, include match name, starttime,endtime,home team name, guest team name .
    
function GetMatchInfo(
        uint256 id      //match id
    ) public view idVaild(id) 
    returns (
        string name,            //match name 
        uint256 startTime,  //start time （UTC）
        uint256 endTime,        // end time （UTC）
        string  homeName,   //home team name
        string  guestName   //guest team name
)   


max match id 

return max match id. 

function GetMatchMaxId() public view returns (uint256)


match state

return match state.   0: Not started  1: in play  2: game over

function GetMatchState(
        uint256 id      // match id
) public view idVaild(id) 
returns (
uint256     //0: Not started  1: in play  2: game over
)


match price

return price to be paid for fetch match score .
 
function GetMatchPrice(
        uint256 id      // match id
) public view idVaild(id) returns (uint256)


match score

return match score

function GetMatchScore(
        uint256 id      // match id
) public payable idVaild(id)  
returns  (
uint8 homeScore,  //home team score
uint8 guestScore    //guest team score
)



