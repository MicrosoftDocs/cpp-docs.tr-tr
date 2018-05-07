---
title: CLR dizisi bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- array keyword [C++]
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8d8b2a5d348887d56a1221a5a9125449e5356b9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="declaration-of-a-clr-array"></a>CLR Dizisi Bildirimi
Bildirme sözdizimi, örnek oluşturma ve yönetilen bir dizi başlatma Yönetilen Uzantılar'dan C++ için Visual C++'a değişmiştir.  
  
 Yönetilen Uzantılar CLR dizi nesnesinin bildirimi standart dizi bildiriminin uzantısı olan bir `__gc` anahtar sözcüğü dizi nesnesinin adını çiftiyle olduğu gibi büyük olasılıkla virgülle doldurulmuş boyutu arasındaki yerleştirildiği Örnekler:  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 Bu C++ Standart Kitaplığı'na benzer bir şablon benzeri bildirimi kullandığımız yeni sözdiziminde basitleştirilmiştir `vector` bildirimi. İlk parametre öğe türünü gösterir. İkinci parametre boyut dizisini belirtir (1 ile bir varsayılan değer, yalnızca birden çok boyut gerektir ikinci bir bağımsız değişken). Dizi nesnesi izleme işleyicisidir ve bu nedenle bir hat verilmelidir. Öğe türü aynı zamanda bir başvuru türü ise bir şapka da gerektirir. Örneğin, yukarıdaki örnekte Yeni sözdiziminde belirtildiğinde, aşağıdaki gibi görünür:  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 Bir başvuru türü bir nesne yerine izleme işleyicisi olduğundan, CLR dizisi işlevinin dönüş türü olarak belirtmek mümkündür. (Buna karşılık, onu yerel diziyi bir işlevin dönüş türü belirlemek mümkün değildir.) Yönetilen Uzantılar'bunu sözdizimi biraz kolay anlaşılamayan. Örneğin:  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 Visual C++'da, bildirim çok daha kolaydır. Örneğin,  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 Yerel ve yönetilen bir dizi toplu başlatma dil her iki sürümünde de desteklenir. Örneğin:  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 Yeni sözdiziminde oldukça Basitleştirilmiş (kutulama yeni sözdiziminde örtük olduğundan unutmayın `__box` işleci ortadan - bkz [değer türleri ve Their davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md) bir tartışma için):  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 Bir dizi CLR başvuru türü olduğundan, her dizi nesnesinin bildirimi izleme işleyicisidir. Bu nedenle, dizi nesneleri CLR yığında ayrılmış gerekir. (Bir toplu notasyona Yönetilen yığın ayırma gizler.) Yönetilen Uzantılar altında bir dizi nesnesi başlatmasının açık formu aşağıdadır:  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 Yeni sözdizimi altında `new` ifade ile değiştirilir `gcnew`. Boyut boyutları için parametre olarak geçirilen `gcnew` şekilde ifade:  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 Yeni sözdiziminde bir açık başlatma listesi izleyebilirsiniz `gcnew` ifade; bu Yönetilen Uzantılar'desteklenmiyordu. Örneğin:  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)   
 [Diziler](../windows/arrays-cpp-component-extensions.md)