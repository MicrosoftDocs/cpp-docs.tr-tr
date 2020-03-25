---
title: Erişimciler ve Satır Kümeleri
ms.date: 11/19/2018
helpviewer_keywords:
- accessors [C++]
- OLE DB consumer templates, rowset support
- OLE DB consumer templates, accessors
- rowsets [C++], accessing
- bulk rowsets
- CAccessorRowset class, accessor types
- single rowsets
- CArrayRowset class, accessors
- CBulkRowset class, accessors
- array rowsets
- CAccessorBase class
- CRowset class, accessors and rowsets
- accessors [C++], rowsets
- rowsets [C++], supported types
ms.assetid: edc9c8b3-1a2d-4c2d-869f-7e058c631042
ms.openlocfilehash: 45180b3ac2647c9f4f5d25a1322794552bd79004
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212387"
---
# <a name="accessors-and-rowsets"></a>Erişimciler ve Satır Kümeleri

OLE DB şablonlar, verileri ayarlamak ve almak için [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) sınıfı aracılığıyla bir erişimci ve bir satır kümesi kullanır. Bu sınıf, farklı türlerde birden çok erişimciyi işleyebilir.

## <a name="accessor-types"></a>Erişimci türleri

Tüm erişimciler [CAccessorBase](../../data/oledb/caccessorbase-class.md)'den türetilir. `CAccessorBase` hem parametre hem de sütun bağlamayı sağlar.

Aşağıdaki şekilde erişimci türleri gösterilmektedir.

![Erişimci türleri](../../data/oledb/media/vcaccessortypes.gif "Erişimci türleri")<br/>
Erişimci sınıfları

- [CAccessor](../../data/oledb/caccessor-class.md) Tasarım zamanında veritabanı kaynağının yapısını bildiğiniz zaman bu erişimciyi kullanın. `CAccessor`, arabelleği içeren bir veritabanı kaydını veri kaynağına statik olarak bağlar.

- [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) Tasarım zamanında veritabanının yapısını bilmiyorsanız bu erişimciyi kullanın. veritabanı sütun bilgilerini almak için `IColumnsInfo::GetColumnInfo` `CDynamicAccessor` çağırır. Bir erişimcisi ve arabelleği oluşturur ve yönetir.

- [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) Bilinmeyen komut türlerini işlemek için bu erişimciyi kullanın. Komutları hazırlarken `CDynamicParameterAccessor`, sağlayıcı `ICommandWithParameters`destekliyorsa, `ICommandWithParameters` arabiriminden parametre bilgilerini alabilir.

- [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md), [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)ve [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md) veritabanı şeması hakkında bilginiz olmadığında bu sınıfları kullanın. `CDynamicStringAccessorA`, verileri ANSI dizeleri olarak alır; `CDynamicStringAccessorW` verileri Unicode dizeleri olarak alır.

- [CManualAccessor](../../data/oledb/cmanualaccessor-class.md) Bu sınıfla, sağlayıcı türü dönüştürebiliyorsanız istediğiniz veri türlerini kullanabilirsiniz. Hem sonuç sütunlarını hem de komut parametrelerini işler.

Aşağıdaki tabloda OLE DB şablonu erişimci türlerindeki destek özetlenmektedir.

|Erişimci türü|Dinamik|Parametreleri işler|Buffer|Birden çok erişimci|
|-------------------|-------------|--------------------|------------|------------------------|
|`CAccessor`|Hayır|Yes|Kullanıcı|Yes|
|`CDynamicAccessor`|Yes|Hayır|OLE DB Şablonları|Hayır|
|`CDynamicParameterAccessor`|Yes|Yes|OLE DB Şablonları|Hayır|
|`CDynamicStringAccessor[A,W]`|Yes|Hayır|OLE DB Şablonları|Hayır|
|`CManualAccessor`|Yes|Yes|Kullanıcı|Yes|

## <a name="rowset-types"></a>Satır kümesi türleri

OLE DB şablonları üç tür satır kümesini destekler (önceki şekle bakın): tek satır kümeleri ( [CRowset](../../data/oledb/crowset-class.md)tarafından uygulanan), toplu satır kümeleri ( [CBulkRowset](../../data/oledb/cbulkrowset-class.md)tarafından uygulanır) ve dizi satır kümeleri ( [CArrayRowset](../../data/oledb/carrayrowset-class.md)tarafından uygulanır). Tek satır kümeleri `MoveNext` çağrıldığında tek bir satır tutamacı getirir. Toplu satır kümeleri, birden çok satır tanıtıcısı getirebilir. Dizi satır kümeleri, dizi sözdizimi kullanılarak erişilebilen satır kümeleridir.

Aşağıdaki şekilde satır kümesi türleri gösterilmektedir.

![RowsetType grafiği](../../data/oledb/media/vcrowsettypes.gif "RowsetType grafiği")<br/>
Satır kümesi sınıfları

[Şema satır kümeleri](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) veri deposundaki verilere erişemez, bunun yerine veri deposuyla ilgili, meta veriler olarak adlandırılan bilgilere erişir. Şema satır kümeleri genellikle veritabanı yapısının derleme zamanında bilinmediği ve çalışma zamanında alınabilmesi gereken durumlarda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)
