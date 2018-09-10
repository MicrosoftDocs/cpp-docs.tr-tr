---
title: COM öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e18f64d48b357ed691f42fc900f68c8e8054776
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317257"
---
# <a name="com-attributes"></a>COM Öznitelikleri
COM öznitelikleri COM Geliştirme ve .NET Framework ortak dil çalışma zamanı geliştirme çeşitli alanlarını desteklemek için kod ekleyin. Stok özellikleri, yöntemleri ve olayları desteklemek için bu alanları aralığından özel arabirim uygulama ve Destek arabirimlerin mevcut. Ayrıca, bileşik ve ActiveX denetimi uygulama için destek bulunabilir.
  
|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](../windows/aggregatable.md)|Bir denetimi başka bir denetim tarafından toplanabilir gösterir.|
|[toplamlar](../windows/aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[coclass](../windows/coclass.md)|COM arabirimi uygulayan bir COM nesnesi oluşturur.|
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[progid](../windows/progid.md)|Bir denetimin program kimliği tanımlar.|
|[rdx](../windows/rdx.md)|Oluşturur veya bir kayıt defteri anahtarı değiştirir.|
|[registration_script](../windows/registration-script.md)|Belirtilen kayıt betiği çalıştırır.|
|[requires_category](../windows/requires-category.md)|Sınıfı için gerekli bileşen kategorilerini belirtir.|
|[support_error_info](../windows/support-error-info.md)|Hata raporlama için hedef nesne destekler.|
|[synchronize](../windows/synchronize.md)|Bir yönteme erişimi eşitler.|
|[İş parçacığı oluşturma](../windows/threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[vi_progid](../windows/vi-progid.md)|Bir denetimi için sürüm bağımsız bir ProgID tanımlar.|
  
## <a name="see-also"></a>Ayrıca Bkz.
 [Gruplara Göre Öznitelikler](../windows/attributes-by-group.md)