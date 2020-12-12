---
description: 'Hakkında daha fazla bilgi edinin: ne tür erişimci kullanacağınızı belirleme'
title: Ne Tür Erişimci Kullanacağınızı Belirleme
ms.date: 05/09/2019
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
ms.openlocfilehash: f41a39e4920fa68ed901c3b33ad71a0ddd3cf8c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287599"
---
# <a name="determining-which-type-of-accessor-to-use"></a>Ne Tür Erişimci Kullanacağınızı Belirleme

Veri türlerini derleme zamanında veya çalışma zamanında bir satır kümesi üzerinde belirleyebilirsiniz.

Derleme zamanında veri türlerini belirlemeniz gerekiyorsa, bir statik erişimci (gibi `CAccessor` ) kullanın.

Çalışma zamanında veri türlerini belirlemeniz gerekiyorsa, dinamik ( `CDynamicAccessor` veya alt öğeleri) veya el ile erişimci ( `CManualAccessor` ) kullanın. Bu gibi durumlarda, `GetColumnInfo` türleri belirleyebilmeniz için, sütun bağlama bilgilerini döndürmek üzere satır kümesinde çağrı yapabilirsiniz.

Aşağıdaki tablo, tüketici şablonlarında sunulan erişimcileri türlerini listeler. Her erişimcinin avantajları ve dezavantajları vardır. Durumunuza bağlı olarak, bir erişimci türü gereksinimlerinize uygun olmalıdır.

|Erişimci sınıfı|Bağlama|Parametre|Yorum|
|--------------------|-------------|---------------|-------------|
|`CAccessor`|COLUMN_ENTRY makrolarıyla bir kullanıcı kaydı oluşturun. Makrolar bu kayıttaki bir veri üyesini erişimciye bağlar. Satır kümesi oluşturulduğunda, sütunların bağlantısı ilişkisiz olamaz.|Evet, PARAM_MAP makro girdisi kullanarak. Bağladıktan sonra parametreler ilişkisiz olamaz.|Küçük miktarda kod nedeniyle en hızlı erişimci.|
|`CDynamicAccessor`|Otomatik.|Hayır.|Bir satır kümesindeki verilerin türünü bilmiyorsanız yararlı olur.|
|`CDynamicParameterAccessor`|Otomatik, ancak [geçersiz kılınabilir](../../data/oledb/overriding-a-dynamic-accessor.md).|Evet, sağlayıcı destekliyorsa `ICommandWithParameters` . Parametreler otomatik olarak bağlanır.|`CDynamicAccessor`Genel saklı yordamları çağırmak için daha yavaştır ancak yararlı olur.|
|`CDynamicStringAccessor[A,W]`|Otomatik.|Hayır.|Veri deposundan erişilen verileri dize verileri olarak alır.|
|`CManualAccessor`|Kullanılarak el ile `AddBindEntry` .|Kullanarak el ile `AddParameterEntry` .|Hızlı Parametreler ve sütunlar yalnızca bir kez bağlanır. Kullanılacak veri türünü belirlersiniz. (Bir örnek için bkz. [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneği.) Veya sürümünden daha fazla kod gerektirir `CDynamicAccessor` `CAccessor` . OLE DB doğrudan çağırmak gibidir.|
|`CXMLAccessor`|Otomatik.|Hayır.|Veri deposundan erişilen verileri dize verileri olarak alır ve XML etiketli veriler olarak biçimlendirir.|

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
