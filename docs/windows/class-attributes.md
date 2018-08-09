---
title: Sınıf öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], class attributes
- class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a2fe111028f952482dbd6b2eedebc157d39a9a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645181"
---
# <a name="class-attributes"></a>Sınıf Öznitelikleri
Aşağıdaki öznitelikler uygulamak [sınıfı](../cpp/class-cpp.md) C++ anahtar sözcüğü.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[toplanabilir](../windows/aggregatable.md)|Sınıf toplama desteklediğini belirtir.|  
|[toplamlar](../windows/aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|  
|[appobject](../windows/appobject.md)|Coclass'ı bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|  
|[Servis talebi](../windows/case-cpp.md)|İle kullanılan [switch_type](../windows/switch-type.md) UNION özniteliği.|  
|[coclass](../windows/coclass.md)|Bir ActiveX denetimi oluşturur.|  
|[com_interface_entry](../windows/com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|  
|[control](../windows/control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|  
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|  
|[db_param](../windows/db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|  
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|  
|[db_table](../windows/db-table.md)|Bir OLE DB tablosu açılır.|  
|[default](../windows/default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|  
|[defaultvtable](../windows/defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|  
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı oluşturur.|  
|[event_source](../windows/event-source.md)|Olay kaynağı oluşturur.|  
|[helpcontext](../windows/helpcontext.md)|Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.|  
|[helpfile](../windows/helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|  
|[Uygulayan](../windows/implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|  
|[implements_category](../windows/implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|  
|[Modülü](../windows/module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|  
|[noncreatable](../windows/noncreatable.md)|Tek başına oluşturulamaz bir nesneyi tanımlar.|  
|[progid](../windows/progid.md)|Bir denetimin program kimliği tanımlar.|  
|[registration_script](../windows/registration-script.md)|Belirtilen kayıt betiği çalıştırır.|  
|[requestedit](../windows/requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|  
|[Kaynak](../windows/source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem `source` özniteliği gösterir üyesi bir nesne döndürür veya `VARIANT` diğer bir deyişle bir olay kaynağı.|  
|[support_error_info](../windows/support-error-info.md)|Hata raporlama için hedef nesne destekler.|  
|[İş parçacığı oluşturma](../windows/threading-cpp.md)|Bir denetim için iş parçacığı modelini belirtir.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|  
|[Sürüm](../windows/version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|  
|[vi_progid](../windows/vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)