---
title: CObject'ten sınıf türetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- DECLARE_DYNCREATE macro [MFC]
- DECLARE_SERIAL macro [MFC]
- macros [MFC], serialization
- serialization [MFC], macros
- DECLARE_DYNAMIC macro [MFC]
- derived classes [MFC], from CObject
- CObject class [MFC], deriving serializable classes
- CObject class [MFC], deriving from
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0b629617c1592387f3f959996fd3e9837242ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="deriving-a-class-from-cobject"></a>CObject'ten Sınıf Türetme
Bu makalede öğesinden bir sınıf türetin için gereken en düşük adımları [CObject](../mfc/reference/cobject-class.md). Diğer `CObject` sınıfı makalelerde, özel yararlanmak için gereken adımlar açıklanmaktadır `CObject` seri hale getirme ve tanılama hata ayıklama desteği gibi özellikleri.  
  
 Tartışmalar içinde `CObject`, arabirim koşulları "dosyası" ve "uygulama dosyası" sık kullanılır. Arabirim dosyası (genellikle üstbilgi dosyası olarak adlandırılan veya. H dosyası) sınıf bildirimi ve sınıfını kullanmak için gerekli diğer bilgileri içerir. Uygulama dosyasını (veya. Sınıf üyesi işlevleri uygulayan kod yanı sıra sınıf tanımını CPP dosyası) içerir. Örneğin, adlı bir sınıf için `CPerson`, kişi adlı bir arabirim dosyası genellikle oluşturursunuz. Bir uygulama dosyasını ve H kişinin adı. CPP. Ancak, uygulamalar arasında paylaşılmaz bazı küçük sınıfları için bazen arabirimi ve tek bir uygulamasına birleştirmek daha kolay olur. CPP dosyası.  
  
 Bir sınıftan türetilirken dört işlevsellik düzeyi arasından seçim yapabilirsiniz `CObject`:  
  
-   Temel işlevler: çalışma zamanı sınıf bilgileri veya seri hale getirme için destek yok ancak tanılama bellek yönetimi içerir.  
  
-   Temel işlevler ayrıca çalışma zamanı sınıf bilgileri için destek.  
  
-   Temel işlevler ayrıca çalışma zamanı sınıf bilgileri ve dinamik oluşturma desteği.  
  
-   Temel işlevler ayrıca çalışma zamanı sınıf bilgileri, dinamik oluşturma ve seri hale getirme için destek.  
  
 Gelecekteki serileştirme gerek beklenen, tekrar (bunlar daha sonra temel sınıflar olarak hizmet verecektir) kullanılmak üzere tasarlanmış sınıfları çalışma zamanı sınıf ve seri hale getirme desteği, en az içermelidir.  
  
 Bildirim ve uygulamasını, türetilen sınıfların içindeki belirli bildirim ve uygulamasını makroları kullanarak işlevsellik düzeyini seçin `CObject`.  
  
 Aşağıdaki tabloda seri hale getirme ve çalışma zamanı bilgileri desteklemek için kullanılan makroları arasındaki ilişkiyi gösterir.  
  
### <a name="macros-used-for-serialization-and-run-time-information"></a>Seri hale getirme ve çalışma zamanı bilgileri için kullanılan makroları  
  
|Kullanılan makrosu|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|  
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|Temel `CObject` işlevi|Hayır|Hayır|Hayır|  
|`DECLARE_DYNAMIC`|Evet|Hayır|Hayır|  
|`DECLARE_DYNCREATE`|Evet|Evet|Hayır|  
|`DECLARE_SERIAL`|Evet|Evet|Evet|  
  
#### <a name="to-use-basic-cobject-functionality"></a>Temel CObject işlevselliği kullanmak için  
  
1.  Sınıfından türetilen için normal C++ söz dizimini kullanın `CObject` (veya türetilen bir sınıftan `CObject`).  
  
     Aşağıdaki örnek, en basit durumda, bir sınıftan türevi gösterir `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]  
  
 Normalde, ancak, bazı geçersiz kılmak istediğiniz `CObject`ait yeni sınıfınıza ayrıntılarını işlemek için üye işlevleri. Örneğin, genellikle geçersiz kılmak istediğiniz `Dump` işlevinin `CObject` sınıfınız içeriği için hata ayıklama çıktısı sağlamak için. Geçersiz kılma hakkında ayrıntılar için `Dump`, makaleye bakın [Tanılama: dökme nesne içeriği](http://msdn.microsoft.com/en-us/727855b1-5a83-44bd-9fe3-f1d535584b59). Geçersiz kılma isteyebilirsiniz `AssertValid` işlevinin `CObject` sınıf nesnelerine veri üyeleri tutarlılığını doğrulamak için özelleştirilmiş sınama sağlamak için. Geçersiz kılmak nasıl bir açıklaması için `AssertValid`, bkz: [MFC assert_valıd ve CObject::AssertValid](http://msdn.microsoft.com/en-us/7654fb75-9e9a-499a-8165-0a96faf2d5e6).  
  
 Makaleyi [işlevselliğini düzeylerini belirtme](../mfc/specifying-levels-of-functionality.md) nasıl işlevsellik, çalışma zamanı sınıf bilgileri, dinamik Nesne oluşturma ve seri hale getirme gibi diğer düzeylerini belirtileceğini açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject Kullanma](../mfc/using-cobject.md)

