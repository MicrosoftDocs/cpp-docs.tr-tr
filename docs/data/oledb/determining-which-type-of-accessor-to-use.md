---
title: Ne Tür Erişimci Kullanacağınızı Belirleme
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
ms.openlocfilehash: 98234852d0577e581135980d6b8e525aeead5dc2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031874"
---
# <a name="determining-which-type-of-accessor-to-use"></a>Ne Tür Erişimci Kullanacağınızı Belirleme

Derleme zamanında veya çalışma zamanında bir satır kümesi veri türlerinde belirleyebilirsiniz.

Veri türleri, derleme zamanında belirlemeniz gerekiyorsa, statik erişimci kullanma (gibi `CAccessor`). El ile veya kullanarak, veri türlerini belirleyebilirsiniz **ATL OLE DB Tüketicisi Sihirbazı**.

Veri türlerini çalışma zamanında belirlemeniz gerekiyorsa, dinamik kullanın (`CDynamicAccessor` veya onun alt öğelerini) veya el ile erişimci (`CManualAccessor`). Bu gibi durumlarda çağırabilirsiniz `GetColumnInfo` şirket içinden belirleyebilirsiniz türleri sütun bağlama bilgileri döndürülecek satır kümesi.

Aşağıdaki tabloda, tüketici şablonlarında sağlanan erişimcileri türlerini listeler. Her bir erişimci avantajları ve dezavantajları vardır. Durumunuza bağlı olarak, bir erişimci türü ihtiyaçlarınıza uygun.

|Erişimci sınıfı|Bağlama|Parametre|Yorum|
|--------------------|-------------|---------------|-------------|
|`CAccessor`|COLUMN_ENTRY makrolar ile bir kullanıcı kaydı oluşturun. Makroları veri üyesi bulunan kaydındaki erişimciye bağlar. Satır kümesi oluşturulduğunda sütunları ilişkisiz yapılamıyor.|Evet, bir PARAM_MAP makrosu girişi kullanarak. Bağlandıktan parametreleri ilişkisiz yapılamıyor.|Az miktarda kod nedeniyle Hızlı erişimcisi.|
|`CDynamicAccessor`|Otomatik.|Hayır.|Bir satır kümesi veri türünü bilmiyorsanız yararlıdır.|
|`CDynamicParameterAccessor`|Otomatik, ancak [geçersiz kılınan](../../data/oledb/overriding-a-dynamic-accessor.md).|Evet, sağlayıcı destekliyorsa `ICommandWithParameters`. Otomatik olarak ilişkili parametreler.|Daha yavaş `CDynamicAccessor` genel saklı yordam çağırma ancak yararlıdır.|
|`CDynamicStringAccessor[A,W]`|Otomatik.|Hayır.|Dize verileri veri deposundan erişilen verileri alır.|
|`CManualAccessor`|El ile kullanarak `AddBindEntry`.|El ile kullanarak `AddParameterEntry`.|Hızlı; Parametreler ve sütun yalnızca bir kez bağlı. Kullanılacak veri türünü belirler. (Bkz [DBVIEWER](https://github.com/Microsoft/VCSamples) örnek bir örnek.) Daha fazla kod gerektirir `CDynamicAccessor` veya `CAccessor`. OLE DB doğrudan çağırma gibi daha fazla.|
|`CXMLAccessor`|Otomatik.|Hayır.|Dize verileri veri deposundan erişilen verileri alır ve olarak XML etiketli veri biçimleri.|

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)