# Лабораторная работа №2.  Основы верстки.
* Выполнила: Зинченко Анна
* Язык программирования: Java

# Что делает приложение?
Этот проект демонстрирует простой пример перехода между экранами (Activity) в Android-приложении при помощи кнопок на главном экране. 
Чтобы запустить проект можно прочитать ["Как запустить"](#как-запустить)

# Функциональность:
Приложение содержит четыре Activity:
  * MainActivity: 
    На этом экране находится кнопки "Activity 2", "Activity 3", "Activity 3", "Выход"
    <div align="left">
  <img src="https://github.com/domosedochka/Laba2/blob/main/Screenshot_2024-11-04-17-25-22-952_com.example.laba2.jpg" width="200" />
</div>

После нажатия на первую кнопку пользователь должен переходить к SecondActivity, его внешний вид представлен ниже:
<div align="left">
  <img src="https://github.com/domosedochka/Laba2/blob/main/Screenshot_2024-11-04-17-25-28-005_com.example.laba2.jpg" width="200" />
</div>

После нажатия на вторую кнопку пользователь должен переходить к ThirdActivity, его внешний вид представлен ниже:
<div align="left">
  <img src="https://github.com/domosedochka/Laba2/blob/main/Screenshot_2024-11-04-17-25-30-852_com.example.laba2.jpg" width="200" />
</div>

После нажатия на третью кнопку пользователь должен переходить к FourthActivity, его внешний вид представлен ниже:
<div align="left">
  <img src="https://github.com/domosedochka/Laba2/blob/main/Screenshot_2024-11-04-17-57-20-640_com.example.laba2.jpg" width="200" />
</div>
При нажатии нна кнопку она окрашивается в светло-зеленый цвет:
<div align="left">
  <img src="https://github.com/domosedochka/Laba2/blob/main/Screenshot_2024-11-04-17-57-25-052_com.example.laba2.jpg" width="200" />
</div>

После нажатия на четвертую кнопку пользователь выходит из приложения.

# Как запустить
1. Загрузка или клонирование репозитория:
* Скачайте файлы проекта (ZIP-архив) и разархивируйте их в удобную папку или клонируйте репозиторий с помощью команды git clone [URL репозитория].

2. Открытие проекта в Android Studio:
* Откройте Android Studio.
* В главном окне выберите "Open an existing Android Studio project".
* Найдите папку, в которую вы скачали или клонировали проект, и выберите файл build.gradle.

3. Запуск приложения:
* В Android Studio, нажмите кнопку "Run" (зеленый треугольник) на панели инструментов.
* Выберите эмулятор или подключенное Android-устройство, на котором вы хотите запустить приложение.
* Дождитесь завершения сборки и запуска приложения.


# Код:
* **MainActivity.java:**
``` package com.example.laba2;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;


public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button button1 = findViewById(R.id.button1);
        Button button2 = findViewById(R.id.button2);
        Button button3 = findViewById(R.id.button3);
        Button button4 = findViewById(R.id.button4);

        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);
            }
        });

        button2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MainActivity.this, ThirdActivity.class);
                startActivity(intent);
            }
        });

        button3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Intent intent = new Intent(MainActivity.this, FourthActivity.class);
                startActivity(intent);
            }
        });

        button4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                finish();
            }
        });
    }
}
```

* **SecondActivity.java:**
```package com.example.laba2;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class SecondActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_second);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}
```

* **ThirdActivity.java:**
```package com.example.laba2;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class ThirdActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_third);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}
```

* **FourthdActivity.java:**
```package com.example.laba2;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class FourthActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_fourth);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}

```

* **activity_main.xml:**
```<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"

    >

    <Button
        android:id="@+id/button1"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:textSize="20sp"
        android:textStyle="bold"
        android:text="Activity 2"
        android:backgroundTint="#B9E4CD"
        app:layout_constraintHeight_percent="0.2"
        app:layout_constraintWidth_percent="0.75"
        app:layout_constraintVertical_bias="0.02"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        />

    <Button
        android:id="@+id/button2"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:textSize="20sp"
        android:textStyle="bold"
        android:text="Activity 3"
        android:backgroundTint="#B9E4CD"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHeight_percent="0.2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button1"
        app:layout_constraintWidth_percent="0.75" />

    <Button
        android:id="@+id/button3"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:textSize="20sp"
        android:textStyle="bold"
        android:text="Activity 4"
        android:backgroundTint="#B9E4CD"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHeight_percent="0.2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button2"
        app:layout_constraintWidth_percent="0.75"
        app:layout_constraintVertical_bias="0.02"/>

    <Button
        android:id="@+id/button4"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:textSize="20sp"
        android:textStyle="bold"
        android:backgroundTint="#B9E4CD"
        android:text="Выход"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHeight_percent="0.2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button3"
        app:layout_constraintWidth_percent="0.75"
        app:layout_constraintVertical_bias="0.02"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```

* **activity_second.xml:**
```<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    android:layout_width="fill_parent"
    android:layout_height="match_parent"
    tools:context=".SecondActivity">

    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:id="@+id/topLinearLayout"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:orientation="horizontal"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 1"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            android:layout_weight="1"
            android:layout_marginEnd="5dp"
            >
        </Button>
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 2"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_weight="1"
            android:layout_marginEnd="5dp">
        </Button>
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 3"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_weight="1"
            >
        </Button>
    </LinearLayout>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:id="@+id/middleLinearLayout"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:orientation="horizontal"
        android:gravity="center"
        app:layout_constraintTop_toBottomOf="@id/topLinearLayout"
        app:layout_constraintBottom_toTopOf="@id/bottomLinearLayout"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 4"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_marginEnd="5dp"
            >
        </Button>
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 5"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent">
        </Button>
    </LinearLayout>
    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:id="@+id/bottomLinearLayout"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:orientation="horizontal"
        android:gravity="bottom"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 6"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_marginEnd="5dp"
            >
        </Button>
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Button 7"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_marginEnd="5dp">
        </Button>
        <Button
            android:layout_width="fill_parent"
            android:layout_height="wrap_content"
            android:text="Button 8"
            android:backgroundTint="#B9E4CD"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            >
        </Button>
    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```

* **activity_third.xml:**
```<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ThirdActivity">



    <RelativeLayout
        android:id="@+id/topRelativeLayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:paddingLeft="16dp"
        android:paddingRight="16dp">

        <Button
            android:id="@+id/buttonLeft"
            android:layout_width="175dp"
            android:layout_height="wrap_content"
            android:text="Left 50%"
            android:backgroundTint="#B9E4CD"
            android:layout_alignParentLeft="true"
            app:layout_constraintLeft_toLeftOf="parent">

        </Button>
        <Button
            android:id="@+id/buttonRight"
            android:layout_width="175dp"
            android:layout_height="wrap_content"
            android:text="Right 50%"
            android:backgroundTint="#B9E4CD"
            android:layout_alignParentRight="true"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_weight="1"
            android:layout_marginRight="5dp">
        </Button>

        <Button
            android:id="@+id/buttonCenterLeft"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Center Left"
            android:backgroundTint="#B9E4CD"
            android:layout_alignParentLeft="true"
            android:layout_centerVertical="true"
            android:layout_marginRight="5dp"/>

        <Button
            android:id="@+id/buttonCenter"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Center"
            android:backgroundTint="#B9E4CD"
            android:layout_toRightOf="@id/buttonCenterLeft"
            android:layout_toLeftOf="@id/buttonCenterRight"
            android:layout_centerVertical="true"/>

        <Button
            android:id="@+id/buttonCenterRight"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Center Right"
            android:backgroundTint="#B9E4CD"
            android:layout_alignParentRight="true"
            android:layout_centerVertical="true"
            android:layout_marginLeft="5dp"/>

        <Button
            android:id="@+id/buttonButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Button"
            android:backgroundTint="#B9E4CD"
            android:layout_alignParentBottom="true"
            android:layout_centerHorizontal="true"/>
    </RelativeLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```


* **activity_fourth.xml:**
```<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FFFFFF"
    tools:context=".FourthActivity">

    <Button
        android:id="@+id/button11"
        android:layout_width="206dp"
        android:layout_height="115dp"
        android:layout_margin="10dp"
        android:backgroundTint="@drawable/button_selector"
        android:elevation="4dp"
        android:padding="16dp"
        android:text="New Button"
        android:textColor="#000000"
        android:textSize="16sp"
        android:textStyle="bold"
        app:cornerRadius="24dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:strokeColor="#505050"
        app:strokeWidth="11dp"
        />



</androidx.constraintlayout.widget.ConstraintLayout>
```
