---
title: CObject'ten Sınıf Türetme
ms.date: 11/04/2016
f1_keywords:
- CObject
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
ms.openlocfilehash: 26fdab5165ca098c5d7813ebf44983c261094449
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328447"
---
# <a name="deriving-a-class-from-cobject"></a>CObject'ten Sınıf Türetme

Öğesinden bir sınıf türetmek gerekli en azından aşağıdaki adımlar bu makalede [CObject](../mfc/reference/cobject-class.md). Diğer `CObject` sınıfı makaleler özgü avantajlarından yararlanmak için gereken adımları açıklar `CObject` seri hale getirme ve tanılama hata ayıklama desteği gibi özellikleri.

İçindeki tartışmalara `CObject`, arabirimi koşulları "file" ve "uygulama dosyası" sıkça kullanılır. Arabirim dosyası (genellikle üst bilgi dosyası adı veya. H dosyası), sınıf bildiriminin ve sınıfını kullanmak için gerekli diğer bilgileri içerir. Uygulama dosyasına (veya. CPP dosyasına) sınıf tanımının yanı sıra, sınıf üyesi işlevleri uygulayan kod içerir. Örneğin, adında bir sınıf için `CPerson`, genellikle kişi adlı bir arabirim dosyası oluşturursunuz. H ile bir uygulama dosyasını kişinin adı. CPP. Ancak, uygulamalar arasında paylaşılmaz bazı küçük sınıfları için bazen tek bir uygulama ve arabirim birleştirmek daha kolay olur. CPP dosyasına.

Dört işlev düzeylerinden bir sınıftan türetilirken seçebilirsiniz `CObject`:

- Temel işlevler: Çalışma süresi sınıf bilgilerine veya seri hale getirme desteği, ancak tanılama bellek yönetimi içerir.

- Temel işlevlerinin yanı sıra çalışma zamanı sınıf bilgileri için destek.

- Temel işlevlerinin yanı sıra çalışma süresi sınıf bilgilerine ve dinamik oluşturma desteği.

- Temel işlevlerinin yanı sıra çalışma süresi sınıf bilgilerine, dinamik oluşturma ve seri hale getirme için destek.

Gelecekteki serileştirme gerek uğrarsa yeniden (bunlar daha sonra temel sınıf olarak hizmet verecek) kullanım için tasarlanmış sınıflarını ve çalışma zamanı sınıf seri hale getirme desteği, en az içermelidir.

İşlevsellik düzeyine bildirimini ve uygulamasını, türetilen sınıfların içindeki belirli bildirimini ve uygulamasını makroları kullanarak seçtiğiniz `CObject`.

Aşağıdaki tablo, seri hale getirme ve çalışma zamanı bilgileri desteklemek için kullanılan makrolar arasındaki ilişkiyi gösterir.

### <a name="macros-used-for-serialization-and-run-time-information"></a>Seri hale getirme ve çalışma zamanı bilgileri için kullanılan makrolar

|Kullanılan makrosu|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator >><br /><br /> CArchive::operator <<|
|----------------|-----------------------|--------------------------------------|-------------------------------------------------------|
|Temel `CObject` işlevi|Hayır|Hayır|Hayır|
|`DECLARE_DYNAMIC`|Evet|Hayır|Hayır|
|`DECLARE_DYNCREATE`|Evet|Evet|Hayır|
|`DECLARE_SERIAL`|Evet|Evet|Evet|

#### <a name="to-use-basic-cobject-functionality"></a>Temel CObject işlevselliği kullanmak için

1. Sizin sınıfınızdan türetmek için normal C++ söz dizimini kullanan `CObject` (veya türetilmiş sınıftan `CObject`).

   Aşağıdaki örnek, en basit örnekte, bir sınıfın türetme gösterir `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/cpp/deriving-a-class-from-cobject_1.h)]

Normalde, ancak, bazı geçersiz kılmak isteyebilirsiniz `CObject`ait yeni sınıfınıza ayrıntılarını işlemek için üye işlevleri. Örneğin, genellikle geçersiz kılmak istediğiniz `Dump` işlevi `CObject` sınıfınızın içeriği için hata ayıklama çıktısı sağlamak için. Geçersiz kılma hakkında ayrıntılar için `Dump`, makaleye göz atın [nesne dökümü özelleştirme](/previous-versions/visualstudio/visual-studio-2010/sc15kz85(v=vs.100)). Geçersiz kılmak isteyebilirsiniz `AssertValid` işlevi `CObject` özelleştirilmiş veri üyeleri sınıf nesnelerinin tutarlılığını doğrulamak için sınama sağlamak için. Geçersiz kılma açıklamasını `AssertValid`, bkz: [MFC assert_valıd ve CObject::AssertValid](reference/diagnostic-services.md#assert_valid).

Makaleyi [düzeyleri işlevi belirterek](../mfc/specifying-levels-of-functionality.md) işlevsellik, çalışma zamanı sınıf bilgileri, dinamik Nesne oluşturma ve seri hale getirme gibi diğer düzeylerini belirtin açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](../mfc/using-cobject.md)
