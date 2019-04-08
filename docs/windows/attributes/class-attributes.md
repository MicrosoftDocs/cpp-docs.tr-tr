---
title: Sınıf öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: d0913d09c51734f5255271c0d06e639810e0cb58
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025422"
---
# <a name="class-attributes"></a>Sınıf Öznitelikleri

Aşağıdaki öznitelikler uygulamak [sınıfı](../../cpp/class-cpp.md) C++ anahtar sözcüğü.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[toplanabilir](aggregatable.md)|Sınıf toplama desteklediğini belirtir.|
|[toplamlar](aggregates.md)|Bir denetim için hedef sınıf toplayan gösterir.|
|[appobject](appobject.md)|Coclass'ı bir tam .exe uygulamayla ilişkili olan ve bu tür kitaplığında coclass'ı özellikleri ve işlevleri genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak tanımlar.|
|[büyük/küçük harf](case-cpp.md)|İle kullanılan [switch_type](switch-type.md) UNION özniteliği.|
|[coclass](coclass.md)|Bir ActiveX denetimi oluşturur.|
|[com_interface_entry](com-interface-entry-cpp.md)|Bir arabirim giriş için bir COM eşlemesi ekler.|
|[ denetimi](control.md)|Kullanıcı tanımlı tür bir denetimi olduğunu belirtir.|
|[özel](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_command](db-command.md)|OLE DB komut oluşturur.|
|[db_param](db-param.md)|Belirtilen üye bağımsız değişkenine bir giriş veya çıkış parametresi ile ilişkilendirir ve değişken sınırlandırır.|
|[db_source](db-source.md)|Bir veri kaynağı için bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açılır.|
|[default](default-cpp.md)|Özel veya dispinterface coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.|
|[defaultvtable](defaultvtable.md)|Bir denetim için varsayılan vtable arabirimi olarak bir arabirim tanımlar.|
|[event_receiver](event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](event-source.md)|Olay kaynağı oluşturur.|
|[helpcontext](helpcontext.md)|Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstringcontext](helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstring](helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[gizli](hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[uygulamalar](implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|
|[implements_category](implements-category.md)|Sınıfı için uygulanan bir bileşen kategorilerini belirtir.|
|[modül](module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|
|[noncreatable](noncreatable.md)|Tek başına oluşturulamaz bir nesneyi tanımlar.|
|[progid](progid.md)|Bir denetimin program kimliği tanımlar.|
|[registration_script](registration-script.md)|Belirtilen kayıt betiği çalıştırır.|
|[requestedit](requestedit.md)|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim.|
|[kaynak](source-cpp.md)|Denetimin kaynak arabirimleri bağlantı noktaları için bir sınıf üzerinde belirtir. Bir özellik veya yöntem `source` özniteliği gösterir üyesi bir nesne döndürür veya `VARIANT` diğer bir deyişle bir olay kaynağı.|
|[support_error_info](support-error-info.md)|Hata raporlama için hedef nesne destekler.|
|[iş parçacığı oluşturma](threading-cpp.md)|Bir denetim için iş parçacığı modelini belirtir.|
|[uuid](uuid-cpp-attributes.md)|Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.|
|[sürüm](version-cpp.md)|Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.|
|[vi_progid](vi-progid.md)|ProgID sürümden bağımsız biçimi belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)