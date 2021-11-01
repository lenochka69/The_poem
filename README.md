# The_poem
package com.example.homework

import android.os.Bundle
import android.os.PersistableBundle
import android.util.Log
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity
import kotlin.random.Random

private const val TAG = "MainActivity"
private const val MY_FILTER_TAG = "My_filter"
private const val KEY = "Key"

class MainActivity : AppCompatActivity() {
    private lateinit var textrandom: TextView
    private lateinit var randomizeButton: Button


    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity)

        randomizeButton = findViewById(R.id.Click)
        textrandom=findViewById(R.id.Mywork)

        if (savedInstanceState != null)
            textrandom.text = savedInstanceState.getString(KEY)
        else
            randomize()

        randomizeButton.setOnClickListener{randomize()}
        Log.d(MY_FILTER_TAG, "onCreate()")

    }
    private fun randomize (){
        val randomValue = Random.nextInt (100)
        textrandom.text= randomValue.toString()
    }


    override fun onStart() {
        super.onStart()
        Log.d(MY_FILTER_TAG,"onStart()")
    }

    override fun onResume() {
        super.onResume()
        Log.d(MY_FILTER_TAG,"onResume()")
    }

    override fun onPause() {
        super.onPause()
        Log.d(MY_FILTER_TAG,"onPause()")
    }

    override fun onStop() {
        super.onStop()
        Log.d(MY_FILTER_TAG,"onStop()")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d(MY_FILTER_TAG,"onDestroy()")
    }

    override fun onSaveInstanceState(outState: Bundle, outPersistentState: PersistableBundle) {
        super.onSaveInstanceState(outState)
        outState.putString(KEY, textrandom.text.toString())
    }
    }
