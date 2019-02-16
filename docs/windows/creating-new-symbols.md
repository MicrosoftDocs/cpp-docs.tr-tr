---
title: 'Nasıl yapılır: Simgeler (C++) oluştur'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.symbol.creating
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
- vc.editors.symbol.resource
helpviewer_keywords:
- New Symbol dialog box [C++]
- symbols [C++], creating
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
- resource symbols
- View Use button
- resource editors [C++], resource symbols
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
ms.openlocfilehash: 01b810d162da4d59c2044fe02a1da5c0929d41b9
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320607"
---
# <a name="how-to-create-symbols-c"></a>Nasıl yapılır: Simgeler (C++) oluştur

Yeni bir proje başlıyor olun ister, atanmış oldukları kaynakları oluşturmadan önce ihtiyacınız sembol adları kullanıma eşleştirmek kullanışlı bulabilirsiniz.

**Kaynak sembolleri** C++ iletişim kutusu, yeni kaynak sembolleri eklemek için görüntülenir ya da sembol kullanımda olduğu konumda kaynak kodu atlamak sembolleri değiştirme olanak tanır.

İletişim kutusunda, aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|--------------------------|------------------------------------------|
|**Ad**|Simgenin adını görüntüler. Daha fazla bilgi için [sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md).|
|**Değer**|Sembolün sayısal değerini görüntüler. Daha fazla bilgi için [sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md).|
|**Kullanımda**|Bu onay kutusu seçildiğinde, simge bir veya daha fazla kaynak tarafından kullanılmakta olduğunu belirtir. Kaynak veya kaynak kutusu tarafından kullanılan listelenir.|
|**Salt okunur sembolleri Göster**|Bu onay kutusu seçildiğinde, salt okunur kaynakları görüntüler. Varsayılan olarak, **kaynak sembolü** iletişim kutusu, kaynak kod dosyanıza yalnızca değiştirilebilir kaynakları görüntüler ancak bu seçenek belirtilmişse, değiştirilebilir kaynakları kalın metin olarak görüntülenir ve salt okunur kaynaklar düz metin olarak görünür.|
|**Tarafından kullanılan**|Kaynak veya kaynak sembolleri listede seçilen sembolünü kullanarak görüntüler. Belirli bir kaynak için düzenleyici taşımak için kaynağı seçin **kullanılan tarafından** kutusuna ve seçin **görünüm kullanımı**.|
|**Yeni**|Açılır **yeni sembol** iletişim kutusunda, ad tanımlamanıza olanak sağlar ve gerekirse, yeni bir sembolik kaynak tanımlayıcısı için bir değer.|
|**Değişiklik**|Açılır **sembol değiştirme** adı ya da bir sembolün değerini değiştirmek izin veren iletişim kutusu. Simge bir denetim veya kaynağı için ise, simge yalnızca ilgili kaynak Düzenleyicisi'nden değiştirilebilir. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).|
|**Görünüm kullanımı**|Karşılık gelen kaynak Düzenleyicisi sembolü içeren kaynak açılır.|

## <a name="create-symbols"></a>Semboller oluşturma

### <a name="to-create-a-new-symbol"></a>Yeni bir sembolü oluşturmak için

1. İçinde **kaynak sembolleri** iletişim kutusunda **yeni**.

1. İçinde **adı** sembol adını yazın.

1. Atanan sembol değeri kabul edin veya yeni bir değer yazın **değer** kutusu.

1. Seçin **Tamam** yeni sembolü sembol listesine eklenecek.

> [!NOTE]
> Zaten bir sembol adı yazarsanız, bu ada sahip bir simge zaten tanımlandı belirten bir ileti kutusu görünür. Aynı ada sahip iki veya daha fazla sembolleri tanımlanamaz, ancak aynı sayısal değere sahip farklı bir simge tanımlayabilirsiniz. Daha fazla bilgi için [sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md) ve [sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md).

### <a name="to-view-resource-symbols"></a>Kaynak sembolleri görüntülemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. Seçin **kaynak sembolleri** kaynak sembolü tabloda görüntülemek için kısayol menüsünden **kaynak sembolleri** iletişim kutusu.

   > [!NOTE]
   > Önceden tanımlanmış semboller görmek için **salt okunur sembolleri Göster** onay kutusu.

### <a name="to-open-the-resource-editor-for-a-given-symbol"></a>Belirli bir sembol için kaynak düzenleyicisini açmak için

Ne zaman, tarama sembolleri **kaynak sembolleri**, belirli bir sembolle nasıl kullanıldığı hakkında daha fazla bilgi isteyebilirsiniz. **Görünüm kullanımı** düğmesi, bu bilgileri almak için hızlı bir yol sağlar.

#### <a name="to-move-to-the-resource-editor-where-a-symbol-is-being-used"></a>Kaynak Düzenleyicisi için bir simge kullanıldığı yerin taşımak için

1. Dosyasındaki bir simge seçin **adı** kutusunun **kaynak sembolleri** iletişim kutusu.

1. İçinde **kullanılan tarafından** kutusunda, ilginizi çeken kaynak türü seçin.

1. Seçin **görünüm kullanımı** düğmesi.

   Kaynak uygun düzenleyici penceresinde görünür.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Tanımlayıcıları (simge)](../windows/symbols-resource-identifiers.md)<br/>
[Semboller yönetme](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)<br/>