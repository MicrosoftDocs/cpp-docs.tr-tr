---
description: 'Daha fazla bilgi edinin: Yöntem öznitelikleri'
title: Yöntem öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- method attributes
- attributes [C++/CLI], reference topics
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
ms.openlocfilehash: 29acb1f92b01e85960bc727c9b3e91f9a52732d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327504"
---
# <a name="method-attributes"></a>Yöntem Öznitelikleri

Aşağıdaki öznitelikler bir sınıf, coclass veya arabirimdeki yöntemler için geçerlidir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[bağlanabilir](bindable.md)|Özelliğin veri bağlamayı desteklediğini belirtir.|
|[call_as](call-as.md)|Uzaktan erişilemeyen bir işlevin uzak bir işlevle eşleştirilmesini sağlar.|
|[Özel](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[db_column](db-column.md)|Belirtilen bir sütunu satır kümesine bağlar.|
|[db_command](db-command.md)|Bir OLE DB komutu oluşturur.|
|[db_param](db-param.md)|Belirtilen üye değişkenini bir giriş veya çıkış parametresiyle ilişkilendirir ve değişkeni ayırır.|
|[db_source](db-source.md)|Bir veri kaynağına bir bağlantı oluşturur.|
|[db_table](db-table.md)|Bir OLE DB tablosu açar.|
|[defaultbind](defaultbind.md)|Nesneyi en iyi şekilde temsil eden tek ve bağlanabilir özelliği gösterir.|
|[defaultcollelem](defaultcollelem.md)|Visual Basic kodu iyileştirmesi için kullanılır.|
|[displaybind](displaybind.md)|Kullanıcıya bağlanabilir olarak görüntülenmesi gereken bir özelliği gösterir.|
|[helpcontext](helpcontext.md)|Kullanıcının **Yardım** dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan BIR bağlam kimliği belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için **Yardım** dosyasının adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.|
|[helpstringcontext](helpstringcontext.md)|Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞINI belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (Yerelleştirme) gerçekleştirmek için kullanılacak DLL 'in adını belirtir.|
|[Lene](hidden.md)|Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.|
|[id](id.md)|Bir üye işlev için bir DISPID belirtir (bir özellik veya bir yöntem, bir arabirim ya da dispınterface).|
|[immediatebind](immediatebind.md)|Veritabanına, veri bağlantılı nesnenin bir özelliğindeki tüm değişikliklerin hemen bildirileceğini bildirir.|
|['ndaki](in-cpp.md)|Çağıran yordamdan çağrılan yordama bir parametre geçirilecek olduğunu gösterir.|
|[Yerel](local-cpp.md)|Arabirim üstbilgisinde kullanıldığında MıDL derleyicisini üst bilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saplamalar üretilmeden önce bir yerel yordam belirler.|
|[nonbrowsable](nonbrowsable.md)|Bir arabirim üyesinin bir özellik tarayıcısında görüntülenmemesi gerektiğini belirtir.|
|[propget](propget.md)|Bir özellik erişimcisi işlevi belirtir.|
|[propput](propput.md)|Bir özellik ayarı işlevini belirtir.|
|[propputref](propputref.md)|Değer yerine başvuru kullanan bir özellik ayarı işlevi belirtir.|
|[ptr](ptr.md)|Bir işaretçiyi tam bir işaretçi olarak belirler.|
|[aralığı](range-cpp.md)|Değerleri çalışma zamanında ayarlanmış olan bağımsız değişkenler veya alanlar için izin verilen değerler aralığını belirtir.|
|[requestedit](requestedit.md)|Özelliğin bildirimi desteklediğini gösterir `OnRequestEdit` .|
|[dığından](restricted.md)|Bir Module, Interface veya dispınterface üyesinin rastgele çağrılamıyor olduğunu belirtir.|
|[satype](satype.md)|Yapının veri türünü belirtir `SAFEARRAY` .|
|[kaynaktaki](source-cpp.md)|Bir sınıftaki bağlantı noktaları için denetimin kaynak arabirimlerini belirtir. Bir özellik veya yöntemde `source` özniteliği, üyenin bir olay kaynağı olan bir nesne veya değişken döndürdüğünü gösterir.|
|[synchronize](synchronize.md)|Hedef yönteme erişimi eşitler.|
|[vararg](vararg.md)|İşlevin değişken sayıda bağımsız değişken alıp alan belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma göre öznitelikler](attributes-by-usage.md)
