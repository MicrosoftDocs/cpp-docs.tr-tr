---
title: CObject'ten Sınıf Türetme
ms.date: 11/04/2016
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
ms.openlocfilehash: f4c01538877d8517cf3394d9e0108ce3a9df2900
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621935"
---
# <a name="deriving-a-class-from-cobject"></a>CObject'ten Sınıf Türetme

Bu makalede, [CObject](reference/cobject-class.md)'ten bir sınıf türetmek için gereken en düşük adımlar açıklanmaktadır. Diğer `CObject` sınıf makalelerinde `CObject` serileştirme ve tanılama hata ayıklama desteği gibi belirli özelliklerden yararlanmak için gereken adımlar açıklanır.

' Deki tartışmalarda `CObject` , "arabirim dosyası" ve "uygulama dosyası" terimleri sıklıkla kullanılır. Arabirim dosyası (genellikle üstbilgi dosyası veya olarak adlandırılır.) H dosyası) sınıf bildirimini ve sınıfını kullanmak için gereken diğer bilgileri içerir. Uygulama dosyası (veya. CPP dosyası) sınıf tanımının yanı sıra sınıf üye işlevlerini uygulayan kodu içerir. Örneğin, adlı bir sınıf için `CPerson` genellıkle kişi adında bir arabirim dosyası oluşturursunuz. H ve Kullanıcı adlı bir uygulama dosyası. CPP. Ancak, uygulamalar arasında paylaşılmayacak bazı küçük sınıflar için, arabirim ve uygulamayı tek bir olarak birleştirmek bazen daha kolay olur. CPP dosyası.

İçinden bir sınıf türetirken dört işlevsellik düzeyinden birini seçebilirsiniz `CObject` :

- Temel işlevsellik: çalışma zamanı sınıf bilgisi veya serileştirme desteği yoktur, ancak tanılama bellek yönetimini içerir.

- Temel işlevler ve çalışma zamanı sınıf bilgileri desteği.

- Temel işlevler ve çalışma zamanı sınıf bilgileri ve dinamik oluşturma desteği.

- Temel işlevler ve çalışma zamanı sınıf bilgileri, dinamik oluşturma ve serileştirme desteği.

Yeniden kullanım için tasarlanan sınıflar (daha sonra temel sınıflar olarak işlev görür), gelecekteki bir serileştirme ihtiyacı varsa, en azından çalışma zamanı sınıfı desteğini ve serileştirme desteğini içermelidir.

' Den türettiğiniz sınıfların bildiriminde ve uygulamasında belirli bildirim ve uygulama makroları kullanarak işlevsellik düzeyini seçersiniz `CObject` .

Aşağıdaki tabloda serileştirme ve çalışma zamanı bilgilerini desteklemek için kullanılan makrolar arasındaki ilişki gösterilmektedir.

### <a name="macros-used-for-serialization-and-run-time-information"></a>Serileştirme ve çalışma zamanı bilgileri için kullanılan makrolar

|Kullanılan makro|CObject:: IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive:: operator>><br /><br /> CArchive:: operator<<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|Temel `CObject` işlevsellik|Hayır|Hayır|Hayır|
|`DECLARE_DYNAMIC`|Evet|Hayır|Hayır|
|`DECLARE_DYNCREATE`|Yes|Yes|Hayır|
|`DECLARE_SERIAL`|Yes|Yes|Yes|

#### <a name="to-use-basic-cobject-functionality"></a>Temel CObject işlevlerini kullanmak için

1. Sınıfınızı `CObject` (veya öğesinden türetilmiş bir sınıftan) türetmek için normal C++ söz dizimini kullanın `CObject` .

   Aşağıdaki örnek, bir sınıfın türetme en basit durumunu gösterir `CObject` :

   [!code-cpp[NVC_MFCCObjectSample#1](codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

Ancak, normal olarak, `CObject` Yeni sınıfınızın özelliklerini işlemek için bazı üye işlevlerini geçersiz kılmak isteyebilirsiniz. Örneğin, `Dump` `CObject` sınıfınızın içeriği için hata ayıklama çıkışı sağlamak üzere genellikle işlevini geçersiz kılmak isteyebilirsiniz. Geçersiz kılma hakkında ayrıntılar için `Dump` , [nesne dökümü özelleştirmesi](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))makalesine bakın. Ayrıca, `AssertValid` `CObject` sınıf nesnelerinin veri üyelerinin tutarlılığını doğrulamak üzere özelleştirilmiş test sağlamak için işlevini geçersiz kılmak isteyebilirsiniz. Nasıl geçersiz kılabileceğiniz hakkında bir açıklama için `AssertValid` bkz. [MFC ASSERT_VALID ve CObject:: AssertValid](reference/diagnostic-services.md#assert_valid).

[Işlev düzeylerini belirleyen](specifying-levels-of-functionality.md) makale, çalışma zamanı sınıf bilgileri, dinamik nesne oluşturma ve serileştirme dahil diğer işlevsellik düzeylerinin nasıl belirtileceğini açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](using-cobject.md)
