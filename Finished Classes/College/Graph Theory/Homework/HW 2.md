1. You and your friends are going on a road trip from Pullman to Atlanta, Georgia. Below is map indicating major cities along the way and the distances between them. Use Dijkstra’s Algorithm to find a shortest path from Pullman to Atlanta.  

*(a)* Show each step of the algorithm.  
*(b)* At each step of the algorithm, include the set of Visited Nodes and the set of Unvisited Nodes.  
*(c)* At each step of the algorithm, include a table that contains (1) the current distance from Pullman to each node and (2) the previous node visited for each node.

## **Step 1**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | ${0}$                 |               |
| Boise       | ${\infty}$              |        |
| Denver      |  ${\infty}$             |        |
| Albuquerque |   ${\infty}$                |               |
| Sioux Falls |  ${\infty}$             |        |
| Kansas City |   ${\infty}$                |               |
| Dallas      |   ${\infty}$                |               |
| Minneapolis |   ${\infty}$           |        |
| Nashville   |    ${\infty}$               |               |
| Atlanta     |    ${\infty}$               |               |

*Visited Nodes*
${V = \{\}}$

*Unvisited Nodes*
${U = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City}, }$
${\text{Nashville}, \text{Dallas}\}}$

## **Step 2**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | ${0}$                 |               |
| Boise       | ${300}$               | Pullman       |
| Denver      | ${1150}$              | Pullman       |
| Albuquerque |    ${\infty}$               |               |
| Sioux Falls | ${1250}$              | Pullman       |
| Kansas City |    ${\infty}$               |               |
| Dallas      |    ${\infty}$               |               |
| Minneapolis | ${1420}$              | Pullman       |
| Nashville   |    ${\infty}$               |               |
| Atlanta     |    ${\infty}$               |               |

*Visited Nodes*
${V = \{\text{Pullman}\}}$

*Unvisited Nodes*
${U = \{\text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City},}$
${\text{Nashville}, \text{Dallas}\}}$

## **Step 3**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise      |
| Albuquerque |    1250               |      Boise         |
| Sioux Falls | 1250              | Pullman       |
| Kansas City |   ${\infty}$                |               |
| Dallas      |   ${\infty}$                |               |
| Minneapolis | 1420              | Pullman       |
| Nashville   |   ${\infty}$                |               |
| Atlanta     |    ${\infty}$               |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}\}}$

*Unvisited Nodes*
${U = \{\text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City}, \text{Nashville}, \text{Dallas}\}}$

## **Step 4**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1720              | Denver   |
| Dallas      |  ${\infty}$                 |               |
| Minneapolis | 1420              | Pullman       |
| Nashville   |  ${\infty}$                 |               |
| Atlanta     |  ${\infty}$                 |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}\}}$

*Unvisited Nodes*
${U = \{\text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City}, \text{Nashville}, \text{Dallas}\}}$

## **Step 5**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |  ${\infty}$                 |               |
| Minneapolis | 1420              | Pullman       |
| Nashville   |  ${\infty}$                 |               |
| Atlanta     |  ${\infty}$                 |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}\}}$

*Unvisited Nodes*
${U = \{\text{Minneapolis}, \text{Albuquerque}, \text{Kansas City}, \text{Nashville}, \text{Dallas}\}}$

## **Step 6**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |  1900              |  Albuquerque             |
| Minneapolis | 1420              | Pullman       |
| Nashville   |  ${\infty}$                 |               |
| Atlanta     |  ${\infty}$                 |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Albuquerque}\}}$

*Unvisited Nodes*
${U = \{\text{Minneapolis}, \text{Kansas City}, \text{Nashville},\text{Dallas}\}}$



## **Step 7**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |   1900                |   Albuquerque            |
| Minneapolis | 1420              | Pullman       |
| Nashville   |   2300                |     Minneapolis          |
| Atlanta     |   ${\infty}$                |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Albuquerque}, \text{Minneapolis}\}}$

*Unvisited Nodes*
${U = \{\text{Kansas City}, \text{Nashville}, \text{Dallas}\}}$

## **Step 8**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |   1900                |   Albuquerque            |
| Minneapolis | 1420              | Pullman       |
| Nashville   |   2160                |     Kansas City         |
| Atlanta     |   ${\infty}$                |               |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City}\}}$

*Unvisited Nodes*
${U = \{\text{Nashville}, \text{Dallas}\}}$

## **Step 9**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |   1900                |   Albuquerque            |
| Minneapolis | 1420              | Pullman       |
| Nashville   |   2160                |     Kansas City         |
| Atlanta     |  2680                 |         Dallas      |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City},}$
${\text{Dallas}\}}$

*Unvisited Nodes*
${U = \{\text{Nashville}\}}$

## **Step 10**

| Node        | Shortest Distance | Previous Node |
| ----------- | ----------------- | ------------- |
| Pullman     | 0                 |               |
| Boise       | 300               | Pullman       |
| Denver      | 1120              | Boise         |
| Albuquerque | 1250              | Boise        |
| Sioux Falls | 1250              | Pullman       |
| Kansas City | 1610              | Sioux Falls   |
| Dallas      |   1900                |   Albuquerque            |
| Minneapolis | 1420              | Pullman       |
| Nashville   |   2160                |     Kansas City         |
| Atlanta     |  2410                 |         Nashville      |

*Visited Nodes*
${V = \{\text{Pullman}, \text{Boise}, \text{Denver}, \text{Sioux Falls}, \text{Minneapolis}, \text{Albuquerque}, \text{Kansas City},}$
${\text{Nashville}, \text{Dallas}\}}$

*Unvisited Nodes*
${U = \{\}}$

*(d)* After completing the algorithm, describe the route of the shortest path from Pullman to Atlanta

Go from Pullman to Sioux Falls to Kansas City to Nashville to Atlanta, for a total of ${2410}$

![[HW 2 2025-01-29 10.36.43.excalidraw|800]]