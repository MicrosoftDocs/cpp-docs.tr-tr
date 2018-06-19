---
title: geçici (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- volatile_cpp
dev_langs:
- C++
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295654586a3fe251526a4764d54f80f3a70c7014
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32423967"
---
# <a name="volatile-c"></a>volatile (C++)
Programda bir nesnenin donanım tarafından değiştirilebileceğini bildirmek için kullanabileceğiniz bir tür niteleyicisi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
volatile declarator ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici bu anahtar sözcük yorumlaması değiştirmek için derleyici anahtarı.  
  
 Visual Studio, hedef mimariye bağlı olarak `volatile` anahtar sözcüğünü farklı olarak yorumlar. ARM, yoksa için **/volatile** derleyici seçeneği belirtildiğinde, derleyici gerçekleştirir gibi **/volatile:iso** belirtildi. Mimari ARM, yoksa dışında **/volatile** derleyici seçeneği belirtildiğinde, derleyici gerçekleştirir gibi **/volatile:ms** belirtilmiş; bu nedenle, mimarileri için dışında ARM biz kesin Belirttiğiniz öneri **/volatile:iso**ve iş parçacıkları arasında paylaşılan bellek ile ilgilenirken açık eşitleme temelleri ve derleyici iç bilgileri kullanın.  
  
 Kesme işleyicileri gibi, zaman uyumsuz işlemler tarafından kullanılan bellek konumlarına erişim sağlamak için `volatile` niteleyicisini kullanabilirsiniz.  
  
 Zaman `volatile` de sahip bir değişken kullanılan [__restrict](../cpp/extension-restrict.md) anahtar sözcüğü, `volatile` önceliklidir.  
  
 `struct` üyesi `volatile` olarak işaretlendiyse, `volatile` tüm yapıya yayılır. Yapının tek bir yönerge kullanarak geçerli mimariye kopyalanabilen bir uzunluğu yoksa, `volatile` o yapıda tamamen kaybolabilir.  
  
 `volatile` anahtar sözcüğü, aşağıdaki koşullardan biri doğru olduğunda alan üzerinde hiçbir etkisi olmayabilir:  
  
-   Geçici alanın uzunluğu bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyutu aşıyor.  
  
-   `struct` içeren en dıştaki uzunluk (veya büyük olasılıkla iç içe geçmiş bir `struct` üyesi ise) bir yönerge kullanarak geçerli mimariye kopyalanabilmesi için en büyük boyut sınırını aşıyor.  
  
 Derleyicinin bellek erişimlerini yeniden sıralamaması için, işlemci önbelleğe alınamaz bellek erişimini yeniden sıralamasa da, önbelleğe alınamaz değişkenler `volatile` olarak işaretlenmelidir.  
  
 Nesnelerden `volatile` olarak bildirilenler belirli iyileştirmelerde kullanılmaz. Çünkü değerleri herhangi bir zamanda değişebilir.  İstek geldiğinde, önceki yönerge aynı nesneden bir değer istese bile, sistem her zaman geçici bir nesnenin geçerli değerini okur.  Ayrıca, nesnenin değeri atama üzerine hemen yazılır.  
  
## <a name="iso-compliant"></a>ISO Uyumlu  
 C# volatile anahtar sözcüğü aşina veya davranışını hakkında bilginiz varsa `volatile` Visual C++ önceki sürümlerde unutmayın, C ++ 11 ISO standart `volatile` anahtar sözcüğü farklıdır ve Visual Studio'da desteklenen zaman [/ Geçici: ISO](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği belirtildi. (ARM için bu varsayılan olarak belirtilir). C++11 ISO Standard kodundaki `volatile` anahtar sözcüğü yalnızca donanım erişimi için kullanılacaktır; iş parçacıkları arası iletişim için kullanmayın. İş parçacığı arası iletişim için mekanizmaları gibi kullandığınız [std::atomic\<T >](../standard-library/atomic.md) gelen [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md).  
  
## <a name="end-of-iso-compliant"></a>ISO Uyumluluğunun Sonu  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Zaman **/volatile:ms** derleyici seçeneği kullanıldığında — ARM dışında mimarileri hedeflenen, varsayılan olarak — koruma yanı sıra geçici nesnelere başvurular arasında sıralama korumak için ek kod derleyici oluşturur Genel diğer nesnelerin referansları sıralaması. Özellikle:  
  
-   Geçici bir nesneye yazma (geçici yazma olarak da bilinir) işleminde Sürüm semantiği vardır; yani bir yönerge dizisindeki geçici bir nesne için yazma işleminden önce olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici yazmadan önce olur.  
  
-   Geçici bir nesneyi okuma (geçici okuma olarak da bilinir) işleminde Alma semantiği vardır; yani bir yönerge dizisindeki geçici bir bellek için okuma işleminden sonra olan bir genel veya statik nesne başvurusu, derlenmiş ikili içindeki geçici okumadan önce olur.  
  
 Bu, bellek kilitleri ve çok iş parçacıklı uygulamaların sürümlerinde geçici nesnelerin kullanılabilmesini sağlar.  
  
> [!NOTE]
>  Ne zaman sağlanan Gelişmiş garanti onu dayanır zaman **/volatile:ms** derleyici seçeneği kullanıldığında, taşınabilir olmayan kodudur.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)