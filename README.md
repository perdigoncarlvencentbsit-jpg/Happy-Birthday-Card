package com.example.happybirthday

import android.media.Image import android.os.Bundle import android.view.Surface import androidx.activity.ComponentActivity import androidx.activity.compose.setContent import androidx.activity.enableEdgeToEdge import androidx.compose.foundation.layout.fillMaxSize import androidx.compose.foundation.layout.padding import androidx.compose.material3.Scaffold import androidx.compose.material3.Text import androidx.compose.runtime.Composable import androidx.compose.ui.tooling.preview.Preview import com.example.happybirthday.ui.theme.HappyBirthdayTheme import androidx.compose.foundation.Image import androidx.compose.foundation.layout.Arrangement import androidx.compose.foundation.layout.Box import androidx.compose.foundation.layout.Column import androidx.compose.ui.res.painterResource import androidx.compose.foundation.layout.fillMaxSize import androidx.compose.foundation.layout.padding import androidx.compose.ui.unit.dp import androidx.compose.ui.Modifier import androidx.compose.material3.Surface import androidx.compose.material3.MaterialTheme import androidx.compose.ui.Alignment import androidx.compose.ui.graphics.BlendMode.Companion.Color import androidx.compose.ui.layout.ContentScale import androidx.compose.ui.text.style.TextAlign import androidx.compose.ui.unit.sp

class MainActivity : ComponentActivity() { override fun onCreate(savedInstanceState: Bundle?) { super.onCreate(savedInstanceState) enableEdgeToEdge() setContent { HappyBirthdayTheme { Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding -> GreetingImages( message = "Happy Birthday Catherine!", from = "From Carl", modifier = Modifier.padding(innerPadding) ) } } } } }

@Composable fun GreetingImages(message: String, from: String, modifier: Modifier = Modifier) { val image = painterResource(R.drawable.androidparty) Box(modifier) { Image( painter = image, contentDescription = null, contentScale = androidx.compose.ui.layout.ContentScale.Crop, alpha = 05F ) GreetingText( message = message, from = from, modifier = Modifier.fillMaxSize() ) } }

@Composable fun GreetingText(message: String, from: String, modifier: Modifier) { Column( modifier = Modifier.padding(8.dp), verticalArrangement = Arrangement.Center ) { Text( text = message, fontSize = 90.sp, lineHeight = 116.sp, textAlign = TextAlign.Center, color = androidx.compose.ui.graphics.Color.Black) Text( text = from, fontSize = 36.sp, modifier = Modifier, color = androidx.compose.ui.graphics.Color.Black) .padding(top = 16.dp) .align(alignment = Alignment.CenterHorizontally)

    }
}
@Preview(showBackground = true) @Composable fun BirthdayCardPreview() { HappyBirthdayTheme { Surface( modifier = Modifier.fillMaxSize(), color = MaterialTheme.colorScheme.background ) { GreetingImages( message = "Happy Birthday Catherine!", from = "From Carl" ) } }

}
