---
title: Yöntem öznitelikleri (C++ COM) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f5f9af9e302b9346b2bd42acdf1e268a59113f7
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789878"
---
# <a name="method-attributes"></a>Yöntem Öznitelikleri

Bir sınıf, coclass'ı veya arabirim yöntemleri aşağıdaki özniteliklere uygulanır.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[bindable](bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|
|[call_as](call-as.md)|Uzak bir işleve eşlenmesi nonremotable işlevi sağlar.|
|[Özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_column](db-column.md)|Belirtilen sütun, satır kümesine bağlar.|
|[db_command](db-command.md)|OLE DB komut oluşturur.|
|[db_param](db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açılır.|
|[defaultbind](defaultbind.md)|En iyi nesneyi temsil eden tek ve bağlanabilir özelliği belirtir.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic kod iyileştirme için kullanılır.|
|[displaybind](displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken özelliği belirtir.|
|[helpcontext](helpcontext.md)|Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.|
|[helpfile](helpfile.md)|Adını ayarlar **yardımcı** bir tür kitaplığı dosyası.|
|[helpstring](helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[helpstringcontext](helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|
|[hidden](hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[id](id.md)|DISPID bir üye işlevinin (bir özelliği ya da bir yöntemde, arabirim veya dispinterface) belirtir.|
|[immediatebind](immediatebind.md)|Veritabanı veri bağlama nesnesinin bir özelliği yapılan tüm değişikliklerin hemen bildirileceğini belirtir.|
|[in](in-cpp.md)|Bir parametrenin çağıran yordamdan çağrılan yordama geçirileceğini gösterir.|
|[Yerel](local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
|[nonbrowsable](nonbrowsable.md)|Bir arabirim üyesi bir özellik tarayıcısında görüntülenmemelidir gösterir.|
|[propget](propget.md)|Bir özelliği erişimci işlevi belirtir.|
|[propput](propput.md)|Bir özellik ayarı işlevi belirtir.|
|[propputref](propputref.md)|Bir değer yerine başvurur bir özellik ayarı işlevi belirtir.|
|[ptr](ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[Aralığı](range-cpp.md)|Bağımsız değişkenler veya değerleri çalışma zamanında ayarlanır alanlar için izin verilen değer aralığı belirtir.|
|[requestedit](requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|
|[restricted](restricted.md)|Bir modül, arabirim veya dispinterface üyesi rasgele çağrılamaz belirtir.|
|[satype](satype.md)|Veri türü belirtir `SAFEARRAY` yapısı.|
|[Kaynak](source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem `source` öznitelik, üyenin bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.|
|[synchronize](synchronize.md)|Hedef yöntemin erişimi eşitler.|
|[vararg](vararg.md)|İşlev, değişken sayıda bağımsız değişken yapmanızı belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)