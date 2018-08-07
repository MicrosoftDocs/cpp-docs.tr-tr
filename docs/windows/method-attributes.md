---
title: Yöntem öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1850507b9d00ab717a2602d4e230968f5222f077
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604287"
---
# <a name="method-attributes"></a>Yöntem Öznitelikleri
Bir sınıf, coclass'ı veya arabirim yöntemleri aşağıdaki özniteliklere uygulanır.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|[bindable](../windows/bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|  
|[call_as](../windows/call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|  
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|  
|[db_column](../windows/db-column.md)|Belirtilen sütun, satır kümesine bağlar.|  
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|  
|[db_param](../windows/db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|  
|[db_source](../windows/db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|  
|[db_table](../windows/db-table.md)|Bir OLE DB tablosu açılır.|  
|[defaultbind](../windows/defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic kod iyileştirme için kullanılır.|  
|[displaybind](../windows/displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|  
|[helpcontext](../windows/helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|  
|[helpfile](../windows/helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|  
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|  
|[helpstringdll](../windows/helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|  
|[hidden](../windows/hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|  
|[id](../windows/id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|  
|[immediatebind](../windows/immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|  
|[in](../windows/in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|  
|[Yerel](../windows/local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|  
|[nonbrowsable](../windows/nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcısında görüntülenmemelidir gösterir.|  
|[propget](../windows/propget.md)|Bir özelliği erişimci işlevi belirtir.|  
|[propput](../windows/propput.md)|Bir özellik ayarı işlevi belirtir.|  
|[propputref](../windows/propputref.md)|Bir değer yerine başvurur bir özellik ayarı işlevi belirtir.|  
|[ptr](../windows/ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|  
|[Aralığı](../windows/range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|  
|[requestedit](../windows/requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|  
|[restricted](../windows/restricted.md)|Bir modül, arabirim veya dispinterface üyesi rasgele çağrılamaz belirtir.|  
|[satype](../windows/satype.md)|Veri türü belirtir `SAFEARRAY` yapısı.|  
|[Kaynak](../windows/source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem `source` öznitelik, üyenin bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.|  
|[synchronize](../windows/synchronize.md)|Hedef yöntemin erişimi eşitler.|  
|[vararg](../windows/vararg.md)|İşlev, değişken sayıda bağımsız değişken yapmanızı belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)