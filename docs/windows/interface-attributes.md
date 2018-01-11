---
title: "Arabirim öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ff84939b3211633e199066e1a38da2e91efb1c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interface-attributes"></a>Arabirim Öznitelikleri
Aşağıdaki öznitelikler uygulamak [arabirimi (veya __interface)](../cpp/interface.md) C++ anahtar sözcüğü.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[async_uuid](../windows/async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyici yönlendirir UUID belirtir.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliklerine tanımlamanıza olanak sağlar.|  
|[dispinterface](../windows/dispinterface.md)|Arabirim dağıtma arabirimi .idl dosyasına yerleştirir.|  
|[dual](../windows/dual.md)|Arabirim çift arabirim .idl dosyasına yerleştirir.|  
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.|  
|[helpcontext](../windows/helpcontext.md)|Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.|  
|[helpfile](../windows/helpfile.md)|Tür Kitaplığı Yardım dosyasının adını ayarlar.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Yardım konusunun Kimliğini bir .hlp veya .chm dosyasında belirtir.|  
|[helpstringdll](../windows/helpstringdll.md)|Belge dize araması (yerelleştirme) gerçekleştirmek için kullanılacak DLL adını belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.|  
|[library_block](../windows/library-block.md)|.İdl dosyanın kitaplığı bloktaki bir yapı yerleştirir.|  
|[Yerel](../windows/local-cpp.md)|MIDL derleyici arabirimi üstbilgisinde kullanıldığında bir üstbilgi oluşturucuyu olarak kullanmanıza olanak sağlar. Tek bir işlev kullanıldığında, kendisi için hiçbir saplamalar oluşturulan yerel bir yordam belirler.|  
|[nonextensible](../windows/nonextensible.md)|Belirleyen `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenen ve çalışma zamanında ek üyeleriyle genişletilemez. Bu öznitelik yalnızca geçerli bir [çift](../windows/dual.md) arabirimi.|  
|[odl](../windows/odl.md)|Arabirim bir nesne Açıklama Dili (ODL) arabirimi olarak tanımlar.|  
|[object](../windows/object-cpp.md)|Özel bir arabirim tanımlar.|  
|[oleautomation](../windows/oleautomation.md)|Arabirim otomasyon ile uyumlu olup olmadığını gösterir.|  
|[pointer_default](../windows/pointer-default.md)|Varsayılan işaretçi özniteliği için tüm işaretçiler görünür üst düzey işaretçileri dışında parametre listelerinde belirtir.|  
|[ptr](../windows/ptr.md)|Bir işaretçi tam bir işaretçi olarak belirler.|  
|[restricted](../windows/restricted.md)|Hangi kitaplık üyeleri rasgele çağrılamaz belirler.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Kitaplık için benzersiz kimlik sağlar|  
  
 Bir arabirim tanımlamak için bu kurallara uymanız gerekir:  
  
-   Çağırma kuralı varsayılandır [__stdcall](../cpp/stdcall.md).  
  
-   Bir belirtmezseniz bir GUID sağlandı.  
  
-   Hiçbir aşırı yüklenmiş yöntemler izin verilir.  
  
 Değil belirtirken [UUID](../windows/uuid-cpp-attributes.md) özniteliği ve aynı arabirim adı farklı öznitelik projelerinde kullanarak, aynı GUID'ye oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)