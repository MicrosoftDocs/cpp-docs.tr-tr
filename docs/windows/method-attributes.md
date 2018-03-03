---
title: "Yöntem öznitelikleri | Microsoft Docs"
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
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2413543e7638f47db13799e0549a415ee92c1c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="method-attributes"></a>Yöntem Öznitelikleri
Aşağıdaki öznitelikler sınıfı, coclass'ı veya arabirim yöntemleri için geçerlidir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|Özellik veri bağlama desteklediğini belirtir.|  
|[call_as](../windows/call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanıza olanak sağlar.|  
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|  
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|  
|[db_param](../windows/db-param.md)|Belirtilen üye değişkeni bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|  
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|  
|[db_table](../windows/db-table.md)|OLE DB tablo açar.|  
|[defaultbind](../windows/defaultbind.md)|En iyi nesneyi temsil eden tek, bağlanabilirse özelliği gösterir.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic kodu iyileştirme için kullanılır.|  
|[displaybind](../windows/displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmelidir bir özelliği belirtir.|  
|[helpcontext](../windows/helpcontext.md)|Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.|  
|[helpfile](../windows/helpfile.md)|Tür Kitaplığı Yardım dosyasının adını ayarlar.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Yardım konusunun Kimliğini bir .hlp veya .chm dosyasında belirtir.|  
|[helpstringdll](../windows/helpstringdll.md)|Belge dize araması (yerelleştirme) gerçekleştirmek için kullanılacak DLL adını belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.|  
|[id](../windows/id.md)|Üye işlevi (bir özellik veya bir arabirim veya görüntüleme arabirimi bir yöntem) için bir DISPID belirtir.|  
|[immediatebind](../windows/immediatebind.md)|Veritabanı veri bağlama nesnenin bir özelliğini yapılan tüm değişiklikler, hemen bildirilecek gösterir.|  
|[in](../windows/in-cpp.md)|Bir parametre çağrılan yordamı çağırma yordamdan geçirilecek olduğunu gösterir.|  
|[Yerel](../windows/local-cpp.md)|MIDL derleyici arabirimi üstbilgisinde kullanıldığında bir üstbilgi oluşturucuyu olarak kullanmanıza olanak sağlar. Tek bir işlev kullanıldığında, kendisi için hiçbir saplamalar oluşturulan yerel bir yordam belirler.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcıda görüntülenmemelidir gösterir.|  
|[propget](../windows/propget.md)|Özellik erişimcisi işlevi belirtir.|  
|[propput](../windows/propput.md)|Bir özellik ayarı işlevi belirtir.|  
|[propputref](../windows/propputref.md)|Bir başvuru yerine bir değer kullanır özellik ayarı işlevi belirtir.|  
|[ptr](../windows/ptr.md)|Bir işaretçi tam bir işaretçi olarak belirler.|  
|[Aralık](../windows/range-cpp.md)|Bağımsız değişken veya değerleri çalışma zamanında ayarlanır alanları için izin verilen değer aralığı belirtir.|  
|[requestedit](../windows/requestedit.md)|Özellik desteklediğini gösterir **OnRequestEdit** bildirim.|  
|[restricted](../windows/restricted.md)|Bir modül, arabirim veya görüntüleme arabirimi üyesi rasgele çağrılamaz belirtir.|  
|[satype](../windows/satype.md)|Veri türünü belirtir **SAFEARRAY** yapısı.|  
|[Kaynak](../windows/source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem **kaynak** öznitelik gösterir üye bir nesneye veya kaynaklı olayların bir Değişken döndürür.|  
|[synchronize](../windows/synchronize.md)|Hedef yöntemin erişimi eşitler.|  
|[vararg](../windows/vararg.md)|İşlev değişken sayıda bağımsız değişken sürmesi belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)