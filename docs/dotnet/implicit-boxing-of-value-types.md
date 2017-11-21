---
title: "Değer türlerini örtük kutulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f489c686a182840e142264476c3906d0cbfe97b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implicit-boxing-of-value-types"></a>Değer Türlerini Örtük Olarak Kutulama
Değer türleri kutulama Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Dil tasarımında, biz özelliğiyle pratik deneyim yerine felsefi bir konum uygulanmaz ve isteğe bağlı olarak uygulamada bir hata oluştu. Benzetme özgün birden çok devralma dil tasarımında, Stroustrup sanal temel sınıf alt nesne içinde bir türetilmiş sınıf oluşturucu başlatılamadı ve bu nedenle sanal temel olarak hizmet veren herhangi bir sınıf gereken dili karar sınıfı, varsayılan bir oluşturucu tanımlamanız gerekir. Bu, sonraki tüm sanal türetme tarafından çağrılan, varsayılan bir oluşturucu olur.  
  
 Sanal taban sınıf hiyerarşisinin paylaşılan sanal alt nesnelerin başlatılması sorumluluğunu ile sonraki her türetme kaydırır sorunudur. İçin bir taban sınıf tanımlarsanız, örneğin, bu arabellek kullanıcı tarafından belirtilen boyutu bir arabellek ayırma hangi başlatma gerektiriyorsa bağımsız değişken olarak oluşturucuya geçirilen. Ardından iki izleyen sanal türetme sağlayın, onları çağıran `inputb` ve `outputb`, her temel sınıf oluşturucu için belirli bir değer sağlar. Ne zaman türetilmiş ı şimdi bir `in_out` her ikisi de sınıfından `inputb` ve `outputb`, paylaşılan sanal temel sınıf alt nesne için bu değerleri hiçbiri sensibly değerlendirmek için izin verilebilir.  
  
 Bu nedenle, özgün dil tasarımında, Stroustrup üye başlatma listesi içindeki bir sanal temel sınıfın türetilmiş sınıf oluşturucu, açık başlatma izin verilmiyor. Bu sorun çözüldüğünde, ancak uygulamada başlatma sanal temel sınıfın doğrudan başlatılmasının mümkün olmadığı oluyor uygulamasına yol açıyordu. Keith nihcl National Institute, sistem durumu, kimin uygulayan adlı SmallTalk koleksiyonu kitaplığının bir ücretsiz sürümünü uygulanan, kendisinin daha esnek bir dil tasarımı gündeme gerekiyordu Stroustrup ikna içinde ilkesine sesli oluştu.  
  
 Nesne odaklı hiyerarşik tasarım prensibi türetilmiş bir sınıf kendisi yalnızca hemen temel sınıflarından özel olmayan uygulamasıyla ilgili tutar. Sanal devralma için esnek başlatma tasarımını desteklemek için Stroustrup Bu ilkeyi ihlal gerekiyordu. Bir hiyerarşideki en çok türetilen sınıf oluşur hiyerarşiye nasıl derin bakılmaksızın tüm sanal alt nesne başlatmaları için sorumluluğu üstlenir. Örneğin, `inputb` ve `outputb` her ikisi de hemen sanal temel sınıf açıkça başlatmaktan sorumludurlar. Zaman `in_out` hem de türetilen `inputb` ve `outputb`, `in_out` sanal taban sınıfı bir kez başlatılması kaldırılır ve başlatma yapılan içinde açık sorumlu olur `inputb` ve `outputb` olduğu gizlenen.  
  
 Bu dil geliştiriciler tarafından ancak karmaşık semantiği, gerekli esneklik sağlar. Biz durum olmaksızın ve basit bir arabirim belirlemek için izin vermek için sanal bir temel sınıf kısıtlarsanız olası bu yükünü hemen yapılandırıldıktan. C++ içinde önerilen tasarım deyim budur. CLR programlamada Arabirim türü ilkesiyle tetiklenir.  
  
 İşte bir basit kod örnek - ve bu durumda, açık paketleme gereksizdir:  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 Gördüğünüz gibi tüm çok paketleme devam ediyor yoktur. Visual C++ altında değer türü örtük olarak kutulama:  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değer türleri ve davranışları (C + +/ CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Kutulama](../windows/boxing-cpp-component-extensions.md)