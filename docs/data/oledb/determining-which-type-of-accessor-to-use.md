---
title: Ne Tür Erişimci Kullanacağınızı Belirleme
ms.date: 05/09/2019
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
ms.openlocfilehash: 31efa36bcd61caa154cd3e4c147ad5ed8728b04c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210996"
---
# <a name="determining-which-type-of-accessor-to-use"></a>Ne Tür Erişimci Kullanacağınızı Belirleme

Veri türlerini derleme zamanında veya çalışma zamanında bir satır kümesi üzerinde belirleyebilirsiniz.

Derleme zamanında veri türlerini belirlemeniz gerekiyorsa, bir statik erişimci kullanın (örneğin, `CAccessor`).

Çalışma zamanında veri türlerini belirlemeniz gerekiyorsa, dinamik (`CDynamicAccessor` veya alt öğeleri) veya el ile erişimci (`CManualAccessor`) kullanın. Bu durumlarda, türleri belirleyebilmeniz için satır kümesi üzerinde `GetColumnInfo` çağırabilirsiniz.

Aşağıdaki tablo, tüketici şablonlarında sunulan erişimcileri türlerini listeler. Her erişimcinin avantajları ve dezavantajları vardır. Durumunuza bağlı olarak, bir erişimci türü gereksinimlerinize uygun olmalıdır.

|Erişimci sınıfı|Bağlama|Parametre|Açıklama|
|--------------------|-------------|---------------|-------------|
|`CAccessor`|COLUMN_ENTRY makrolarıyla bir kullanıcı kaydı oluşturun. Makrolar bu kayıttaki bir veri üyesini erişimciye bağlar. Satır kümesi oluşturulduğunda, sütunların bağlantısı ilişkisiz olamaz.|Evet, PARAM_MAP makro girdisi kullanarak. Bağladıktan sonra parametreler ilişkisiz olamaz.|Küçük miktarda kod nedeniyle en hızlı erişimci.|
|`CDynamicAccessor`|Otomatik.|Hayır.|Bir satır kümesindeki verilerin türünü bilmiyorsanız yararlı olur.|
|`CDynamicParameterAccessor`|Otomatik, ancak [geçersiz kılınabilir](../../data/oledb/overriding-a-dynamic-accessor.md).|Evet, sağlayıcı `ICommandWithParameters`destekliyorsa. Parametreler otomatik olarak bağlanır.|`CDynamicAccessor` daha yavaştır, ancak genel saklı yordamları çağırmak için faydalıdır.|
|`CDynamicStringAccessor[A,W]`|Otomatik.|Hayır.|Veri deposundan erişilen verileri dize verileri olarak alır.|
|`CManualAccessor`|`AddBindEntry`kullanarak el ile.|`AddParameterEntry`kullanarak el ile.|Hızlı Parametreler ve sütunlar yalnızca bir kez bağlanır. Kullanılacak veri türünü belirlersiniz. (Bir örnek için bkz. [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneği.) `CDynamicAccessor` veya `CAccessor`daha fazla kod gerektirir. OLE DB doğrudan çağırmak gibidir.|
|`CXMLAccessor`|Otomatik.|Hayır.|Veri deposundan erişilen verileri dize verileri olarak alır ve XML etiketli veriler olarak biçimlendirir.|

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
