---
title: "COM öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- attributes [COM]
- COM, attributes
ms.assetid: 52a5dd70-e8be-4bba-afd6-daf90fe689a0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63e23f6a6520085ff5a5a072cb349d079615b6f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="com-attributes"></a>COM Öznitelikleri
COM öznitelikleri COM Geliştirme ve .NET Framework ortak dil çalışma zamanı geliştirme çeşitli alanlar desteklemek için kod yerleştirir. Stok özellikleri, yöntemleri ve olayları desteklemek için bu alanları aralığından özel arabirim uygulamasına ve var olan arabirimler desteği. Ayrıca, destek bileşik ve ActiveX denetimi uyarlamasını bulunabilir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[toplanabilir](../windows/aggregatable.md)|Bir denetim başka bir denetim tarafından toplanan olduğunu gösterir.|  
|[toplamlar](../windows/aggregates.md)|Bir denetim hedef sınıf toplayan gösterir.|  
|[coclass](../windows/coclass.md)|COM arabirimi uygulayan bir COM nesnesi oluşturur.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş COM Haritası ekler.|  
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bileşen kategorileri belirtir.|  
|[progid](../windows/progid.md)|Bir denetim için ProgID tanımlar.|  
|[rdx](../windows/rdx.md)|Oluşturur veya bir kayıt defteri anahtarı değiştirir.|  
|[registration_script](../windows/registration-script.md)|Belirtilen kayıt betik yürütür.|  
|[requires_category](../windows/requires-category.md)|Sınıfı için gerekli bir bileşen kategorilerini belirtir.|  
|[support_error_info](../windows/support-error-info.md)|Hata raporlama için hedef nesne destekler.|  
|[synchronize](../windows/synchronize.md)|Bir yöntem erişimi eşitler.|  
|[iş parçacığı oluşturma](../windows/threading-cpp.md)|Bir COM nesnesi için iş parçacığı modelini belirtir.|  
|[vi_progid](../windows/vi-progid.md)|Bir denetim için sürüm bağımsız bir ProgID tanımlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gruplara Göre Öznitelikler](../windows/attributes-by-group.md)