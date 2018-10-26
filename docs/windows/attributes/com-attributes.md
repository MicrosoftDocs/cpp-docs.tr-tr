---
title: COM öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
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
ms.openlocfilehash: 2aa88f88fe26b96202f2a917bddf5c8bb07c0d3c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071134"
---
# <a name="com-attributes"></a>COM Öznitelikleri

COM öznitelikleri COM Geliştirme ve .NET Framework ortak dil çalışma zamanı geliştirme çeşitli alanlarını desteklemek için kod ekleyin. Stok özellikleri, yöntemleri ve olayları desteklemek için bu alanları aralığından özel arabirim uygulama ve Destek arabirimlerin mevcut. Ayrıca, bileşik ve ActiveX denetimi uygulama için destek bulunabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Bir denetimi başka bir denetim tarafından toplanabilir gösterir.|
|[toplamlar](aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[coclass](coclass.md)|COM arabirimi uygulayan bir COM nesnesi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[implements_category](implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[progid](progid.md)|Bir denetimin program kimliği tanımlar.|
|[rdx](rdx.md)|Oluşturur veya bir kayıt defteri anahtarı değiştirir.|
|[registration_script](registration-script.md)|Belirtilen kayıt betiği çalıştırır.|
|[requires_category](requires-category.md)|Sınıfı için gerekli bileşen kategorilerini belirtir.|
|[support_error_info](support-error-info.md)|Hata raporlama için hedef nesne destekler.|
|[synchronize](synchronize.md)|Bir yönteme erişimi eşitler.|
|[threading](threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|
|[vi_progid](vi-progid.md)|Bir denetimi için sürüm bağımsız bir ProgID tanımlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Gruplara Göre Öznitelikler](attributes-by-group.md)