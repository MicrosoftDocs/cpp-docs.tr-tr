---
title: "Sınıf öznitelikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d6883774f6deeae2d8c372b68362c743d206eb9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="class-attributes"></a>Sınıf Öznitelikleri
Aşağıdaki öznitelikler uygulamak [sınıfı](../cpp/class-cpp.md) C++ anahtar sözcüğü.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[toplanabilir](../windows/aggregatable.md)|Sınıf toplama desteklediğini belirtir.|  
|[Toplamalar](../windows/aggregates.md)|Bir denetim hedef sınıf toplayan gösterir.|  
|[appobject](../windows/appobject.md)|Bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak coclass'ı tanımlar.|  
|[durumu](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) UNION özniteliği.|  
|[coclass'ı](../windows/coclass.md)|ActiveX denetimi oluşturur.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş COM Haritası ekler.|  
|[denetimi](../windows/control.md)|Kullanıcı tanımlı tür denetim olduğunu belirtir.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|  
|[db_param](../windows/db-param.md)|Belirtilen üye değişkeni bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|  
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|  
|[db_table](../windows/db-table.md)|OLE DB tablo açar.|  
|[Varsayılan](../windows/default-cpp.md)|Özel veya görüntüleme arabirimi coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|  
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|  
|[event_receiver](../windows/event-receiver.md)|Olay alıcısı oluşturur.|  
|[event_source](../windows/event-source.md)|Bir olay kaynağı oluşturur.|  
|[HelpContext](../windows/helpcontext.md)|Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.|  
|[HelpFile](../windows/helpfile.md)|Tür Kitaplığı Yardım dosyasının adını ayarlar.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Yardım konusunun Kimliğini bir .hlp veya .chm dosyasında belirtir.|  
|[HelpString](../windows/helpstring.md)|Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.|  
|[Gizli](../windows/hidden.md)|Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.|  
|[uygular](../windows/implements-cpp.md)|IDL coclass'ı üyeleri olmaya zorlanıp gönderme arabirimleri belirtir.|  
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bileşen kategorileri belirtir.|  
|[Modülü](../windows/module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|  
|[noncreatable](../windows/noncreatable.md)|Tek başına başlatılamaz bir nesneyi tanımlar.|  
|[ProgID](../windows/progid.md)|Bir denetim için ProgID tanımlar.|  
|[registration_script](../windows/registration-script.md)|Belirtilen kayıt betik yürütür.|  
|[requestedit](../windows/requestedit.md)|Özellik desteklediğini gösterir **OnRequestEdit** bildirim.|  
|[Kaynak](../windows/source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem **kaynak** öznitelik gösterir üye bir nesneye veya kaynaklı olayların bir Değişken döndürür.|  
|[support_error_info](../windows/support-error-info.md)|Hata raporlama için hedef nesne destekler.|  
|[iş parçacığı oluşturma](../windows/threading-cpp.md)|Bir denetim için iş parçacığı modelini belirtir.|  
|[UUID](../windows/uuid-cpp-attributes.md)|Sınıfta veya arabirimde benzersiz Kimliğini belirtir.|  
|[Sürüm](../windows/version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|  
|[vi_progid](../windows/vi-progid.md)|Sürüm bağımsız form ProgID belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma göre öznitelikler](../windows/attributes-by-usage.md)