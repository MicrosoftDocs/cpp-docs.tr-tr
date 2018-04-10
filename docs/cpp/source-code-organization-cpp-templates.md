---
title: Kaynak kodu kuruluş (C++ Şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 50569c5d-0219-4966-9bcf-a8689074ad1d
caps.latest.revision: 5
manager: ghogen
ms.openlocfilehash: 1b3b17c17bad3834774f747548dda6710e178cb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="source-code-organization-c-templates"></a>Kaynak kodu kuruluş (C++ Şablonları)

Sınıf şablonu tanımlarken, bunları gerektiğinde üye tanımları derleyiciye görünür şekilde kaynak kodu düzenlemeniz gerekir.   Kullanma seçeneğiniz *ekleme modeli* veya *açık örnekleme* modeli. Ekleme modelinde, bir şablonu kullanan her dosyada üye tanımlarını içerir. Bu yaklaşımın en kolayıdır ve hangi somut türleri, şablonunuzla kullanılabilir bakımından en büyük esneklik sağlar. Kendi dezavantajı, derleme sürelerini artırabilir ' dir. Proje, önemli etkisi olabilir ve/veya eklenen dosyalar büyük. Açık örnekleme yaklaşımda somut sınıflar ya da sınıf üyeleri belirli türleri için şablon örneği oluşturur.  Bu yaklaşım derleme sürelerini hızlandırabilir ancak kullanım, şablonu uygulayan önceden etkinleştirilmiş sınıfları için sınırlar. Genel olarak, derleme sürelerini bir sorun haline sürece dahil etme modeli kullanmanızı öneririz.  
  
## <a name="background"></a>Arka Plan

 Şablonlar gibi sıradan sınıfları derleyici bir şablonu veya tüm üyeleri için nesne kodu oluşturmaz herkese açık değildir. Şablon somut türleri ile örneği kadar oluşturmak için hiçbir şey yoktur. Derleyici karşılaştığında şablonu örneklemesi gibi `MyClass<int> mc;` ve hiçbir sınıfı bu imza ile henüz yok, yeni bir sınıf oluşturur. Kullanılan tüm üye işlevleri kodunu oluşturmak de çalışır. Bu tanımları olmayan bir dosya olup olmadığını #, doğrudan veya dolaylı olarak derleniyor, .cpp dosyasında included derleyici bunları göremez.  İşlevler içinde durumda bağlayıcı bunları bulacaksınız başka bir çeviri biriminde tanımlanan çünkü derleyicinin açısından bakıldığında, bu mutlaka bir hata değildir.  Bağlayıcı bu kodu bulamazsa başlatır bir **çözümlenmemiş dış** hata.  

## <a name="the-inclusion-model"></a>Ekleme modeli

 Şablonu tanımlarını bir çeviri birim boyunca görünür hale getirmek için basit ve en yaygın yoludur üstbilgi dosyası kendisini tanımları yerleştirilecek.  Gereken yalnızca şablonu kullanan herhangi bir .cpp dosyayı # include. Bu standart Kitaplığı'nda kullanılan yaklaşımdır.  
  
```cpp
#ifndef MYARRAY  
#define MYARRAY  
#include <iostream>  
  
template<typename T, size_t N>  
class MyArray  
{  
    T arr[N];  
public:  
    // Full definitions:  
    MyArray(){}  
    void Print()  
    {  
        for (const auto v : arr)  
        {  
            std::cout << v << " , ";  
        }  
    }  
  
    T& operator[](int i)  
   {  
       return arr[i];  
   }   
};  
#endif  
```  
  
 Bu yaklaşımı Derleyici tam şablon tanımının erişimi vardır ve herhangi bir tür için isteğe bağlı şablonları örneğini oluşturabilirsiniz. Basit ve sürdürmek daha kolaydır. Ancak, ekleme modeli bir maliyet açısından derleme sürelerini sahip.   Bu maliyet büyük programlarda önemli özellikle şablonu başlığı # diğer üstbilgileri includes. Her .cpp dosya #includes üstbilgi işlev şablonları ve tüm tanımları kendine ait kopyasını alır. Bağlayıcı genellikle şey, işlevi için birden fazla tanımı şunun değil, ancak bu iş yapmak için zaman alır şekilde Sırala mümkün olacaktır. Ek derleme süresi önemli olduğunu büyük olasılıkla daha küçük programlarda.  
  
## <a name="the-explicit-instantiation-model"></a>Açık örnekleme modeli

 Ekleme modeli projeniz için uygun değil ve bir şablon örneği oluşturmak için kullanılan türleri kümesini tam olarak biliyorsanız sonra şablonu kodu .h ve .cpp dosyasına dışarı ayırın ve .cpp dosyasında açıkça şablonları örneği. Derleyici kullanıcı örneklemesi karşılaştığında görürsünüz bu nesne kodu oluşturulmasına neden olur.  
  
 Açık örnekleme örneği oluşturmak için istediğiniz varlığı imzaya göre ardından anahtar sözcüğü şablonu kullanarak oluşturun. Bu, bir tür veya üye olabilir. Açıkça bir türü örneği varsa, tüm üyeler oluşturulur.  
  
```cpp
template MyArray<double, 5>;  
```  
  
```cpp
//MyArray.h  
#ifndef MYARRAY  
#define MYARRAY  
  
template<typename T, size_t N>  
class MyArray  
{  
    T arr[N];  
public:  
    MyArray();  
    void Print();  
    T& operator[](int i);  
};  
#endif  
  
//MyArray.cpp  
#include "stdafx.h"  
#include <iostream>  
#include "MyArray.h"  
  
using namespace std;  
  
template<typename T, size_t N>  
MyArray<T,N>::MyArray(){}  
  
template<typename T, size_t N>  
void MyArray<T,N>::Print()  
{  
    for(const auto v : arr)  
    {  
        cout << v << "'";  
    }  
    cout << endl;  
}  
  
template MyArray<double, 5>;template MyArray<string, 5>;  
```  
  
 Önceki örnekte, açık örneklemesi .cpp dosyanın sonunda ' dir. A `MyArray` yalnızca için kullanılabilir **çift** veya **dize** türleri.  
  
> [!NOTE]
>  C ++ 11 **verme** anahtar sözcüğü şablonu tanımlarını bağlamında kullanım. Çoğu derleyicileri formu hiçbir zaman desteklenmediğinden pratikteki bu çok az etkisi vardır.
