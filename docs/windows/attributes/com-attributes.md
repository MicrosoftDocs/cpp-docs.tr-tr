---
title: COM Öznitelikleri
ms.date: 10/03/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
ms.openlocfilehash: 15225d23abb66b8aadd5f82b8429334356bdaa8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168323"
---
# <a name="com-attributes"></a>COM Öznitelikleri

COM öznitelikleri, COM Geliştirme ve .NET Framework ortak dil çalışma zamanı geliştirme 'nin çok sayıda alanını desteklemek için kod ekler. Bu alan, özel arabirim uygulamasından ve mevcut arabirimlerin destek stok özelliklerini, yöntemlerini ve olaylarını desteklemeye yönelik olarak değişir. Ayrıca, Birleşik ve ActiveX denetim uygulamasına yönelik destek bulunabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Bir denetimin başka bir denetim tarafından toplanamayacağını gösterir.|
|[toplamlar](aggregates.md)|Bir denetimin hedef sınıfı topladığını gösterir.|
|[coclass](coclass.md)|COM arabirimini uygulayabilen bir COM nesnesi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|COM eşlemesine bir arabirim girişi ekler.|
|[implements_category](implements-category.md)|Sınıf için uygulanan bileşen kategorilerini belirtir.|
|[progid](progid.md)|Bir denetim için ProgID tanımlar.|
|[rdx](rdx.md)|Bir kayıt defteri anahtarı oluşturur veya değiştirir.|
|[registration_script](registration-script.md)|Belirtilen kayıt betiğini yürütür.|
|[requires_category](requires-category.md)|Sınıf için gerekli bileşen kategorilerini belirtir.|
|[support_error_info](support-error-info.md)|Hedef nesne için hata raporlamayı destekler.|
|[synchronize](synchronize.md)|Bir yönteme erişimi eşitler.|
|[threading](threading-cpp.md)|COM nesnesi için iş parçacığı modelini belirtir.|
|[vi_progid](vi-progid.md)|Bir denetim için sürümden bağımsız bir ProgID tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Gruplara Göre Öznitelikler](attributes-by-group.md)
