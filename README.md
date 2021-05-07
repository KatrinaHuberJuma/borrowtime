# borrowtime
https://nodejs.org/en/docs/guides/getting-started-guide/
https://docs.mongodb.com/manual/core/data-modeling-introduction/
https://docs.mongodb.com/manual/core/data-model-design/#std-label-data-modeling-referencing

<!-- Todo app that dynamically adjusts subsequent tasks to accommodate unexpected schedule changes. MongoDB, Mongoose, Express, Node, React
Leveraged MongoDB for streamlined updates and a document structure flexible enough to achieve my desired functionality. -->

mvp: just display a calendar / day I guess? with tasks
later: have tasks that are of set length and tasks that are borrowable

run api:
    borrowtime/api/bin$ node www

run client (for now):
    borrowtime/client$ npm start

=================================    

// todos 
{
    "high_priority": [],
    "medium": [],
    "low": [],
    "will_expire": []
    "completed": []
}

// day:
{
    "day_id": <id>,
    "date": date,
    "tasks": []
}

// task:
{
    "task_id": <id>,
    "title": string,
    "description": string,
    "optional": boolean,              // can i straight up cancel this task?
    "start_time": time,
    "deadline": datetime,
    "flexible_start": boolean,
    "end_time": time,
    "flexible_end": boolean,
    "min_duration": number,
    "max_duration": number,
    "concurrent": boolean,            // can multitask
    "sub_tasks": [],
    "completed": boolean
}

// if user is running out of time, show array of optional tasks to eliminate