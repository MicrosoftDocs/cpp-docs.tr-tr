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
ms.openlocfilehash: 860af88512acb33ff3035b3a04609165953d80a8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446967"
---
# <a name="deriving-a-class-from-cobject"></a>CObject'ten Sınıf Türetme

Bu makalede, [CObject](../mfc/reference/cobject-class.md)'ten bir sınıf türetmek için gereken en düşük adımlar açıklanmaktadır. Diğer `CObject` sınıf makaleleri serileştirme ve tanılama hata ayıklama desteği gibi belirli `CObject` özelliklerden yararlanmak için gereken adımları anlatmaktadır.

`CObject`tartışmalarında, "arabirim dosyası" ve "uygulama dosyası" terimleri sıklıkla kullanılır. Arabirim dosyası (genellikle üstbilgi dosyası veya olarak adlandırılır.) H dosyası) sınıf bildirimini ve sınıfını kullanmak için gereken diğer bilgileri içerir. Uygulama dosyası (veya. CPP dosyası) sınıf tanımının yanı sıra sınıf üye işlevlerini uygulayan kodu içerir. Örneğin, `CPerson`adlı bir sınıf için genellikle kışı adında bir arabirim dosyası oluşturursunuz. H ve Kullanıcı adlı bir uygulama dosyası. CPP. Ancak, uygulamalar arasında paylaşılmayacak bazı küçük sınıflar için, arabirim ve uygulamayı tek bir olarak birleştirmek bazen daha kolay olur. CPP dosyası.

`CObject`bir sınıf türetirken dört işlev düzeyi arasından seçim yapabilirsiniz:

- Temel işlevsellik: çalışma zamanı sınıf bilgisi veya serileştirme desteği yoktur, ancak tanılama bellek yönetimini içerir.

- Temel işlevler ve çalışma zamanı sınıf bilgileri desteği.

- Temel işlevler ve çalışma zamanı sınıf bilgileri ve dinamik oluşturma desteği.

- Temel işlevler ve çalışma zamanı sınıf bilgileri, dinamik oluşturma ve serileştirme desteği.

Yeniden kullanım için tasarlanan sınıflar (daha sonra temel sınıflar olarak işlev görür), gelecekteki bir serileştirme ihtiyacı varsa, en azından çalışma zamanı sınıfı desteğini ve serileştirme desteğini içermelidir.

`CObject`türettiğiniz sınıfların bildiriminde ve uygulamasında belirli bildirim ve uygulama makroları kullanarak işlevsellik düzeyini seçersiniz.

Aşağıdaki tabloda serileştirme ve çalışma zamanı bilgilerini desteklemek için kullanılan makrolar arasındaki ilişki gösterilmektedir.

### <a name="macros-used-for-serialization-and-run-time-information"></a>Serileştirme ve çalışma zamanı bilgileri için kullanılan makrolar

|Kullanılan makro|CObject:: IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive:: operator > ><br /><br /> CArchive:: operator < <|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|Temel `CObject` işlevselliği|Hayır|Hayır|Hayır|
|`DECLARE_DYNAMIC`|Yes|Hayır|Hayır|
|`DECLARE_DYNCREATE`|Yes|Yes|Hayır|
|`DECLARE_SERIAL`|Yes|Yes|Yes|

#### <a name="to-use-basic-cobject-functionality"></a>Temel CObject işlevlerini kullanmak için

1. Sınıfınızı `CObject` ( C++ veya `CObject`türetilmiş bir sınıftan) türetmek için normal sözdizimini kullanın.

   Aşağıdaki örnek, `CObject`bir sınıfın Türetmenin en basit durumunu göstermektedir:

   [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

Ancak, normal olarak, Yeni sınıfınızın özelliklerini işlemek için `CObject`üye işlevlerinin bazılarını geçersiz kılmak isteyebilirsiniz. Örneğin, sınıfınızın içeriği için hata ayıklama çıkışı sağlamak üzere genellikle `CObject` `Dump` işlevini geçersiz kılmak isteyebilirsiniz. `Dump`geçersiz kılma hakkında daha fazla bilgi için, [nesne dökümü özelleştirmesi](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100))makalesine bakın. Ayrıca, sınıf nesnelerinin veri üyelerinin tutarlılığını doğrulamak üzere özelleştirilmiş test sağlamak için `CObject` `AssertValid` işlevini geçersiz kılmak isteyebilirsiniz. `AssertValid`nasıl geçersiz kılabileceğiniz hakkında bir açıklama için bkz. [MFC ASSERT_VALID ve CObject:: AssertValid](reference/diagnostic-services.md#assert_valid).

[Işlev düzeylerini belirleyen](../mfc/specifying-levels-of-functionality.md) makale, çalışma zamanı sınıf bilgileri, dinamik nesne oluşturma ve serileştirme dahil diğer işlevsellik düzeylerinin nasıl belirtileceğini açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](../mfc/using-cobject.md)
