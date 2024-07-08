# model.User.megaproject.schema.mongo
const mongoose =require("mongoose");

// trim being used to remove white spaces , cources bhot hi jada hai toh array structure use kiya haiii....object is se jitne bhi hai voh sare api database hai
const courseSchema = new mongoose.Schema({
    courceName:{
        type:String,
        trim:true,
        required:true,
    },
    courseDescription:{
        type:String,
        trim:true,
    },
    instructor:{
        type:mongoose.Schema.Types.ObjectId,
        ref:"User",
        required:true,
    },
    whatYouWillLearn:{
        type:String,
    },
    courseContent:[
        {
            type:mongoose.Schema.Types.ObjectId,
            ref:"Section"
        }
    ],
    ratingAndReviews:[
        {
            type:mongoose.Schema.Types.ObjectId,
            ref:"RatingAndReview",
        }
    ],
    price:{
        type:Number,

    },
    thumbnail:{
        type:String,
    },
    tag:{
        type:mongoose.Schema.Types.ObjectId,
        ref:"Tag"
    },
    studentsEnrolled:[
        {
            type:mongoose.Schema.Types.ObjectId,
            ref:"User",
            required:true
        }
    ]


    

    

    

  
   

});




module.exports=mongoose.model("Course",courseSchema);
