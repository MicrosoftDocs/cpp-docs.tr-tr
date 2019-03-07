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
ms.openlocfilehash: 91092b29d7265904e69b093310daa72b673d8745
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563387"
---
# <a name="how-to-create-symbols-c"></a>Nasıl yapılır: Simgeler (C++) oluştur

Yeni bir proje başlıyor olun ister, atanmış oldukları kaynakları oluşturmadan önce ihtiyacınız sembol adları kullanıma eşleştirmek kullanışlı bulabilirsiniz.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [nasıl yapılır: Kaynakları oluşturma](../windows/how-to-create-a-resource-script-file.md).

**Kaynak sembolleri** iletişim kutusu, yeni kaynak sembolleri eklemek için görüntülenen ya da sembol kullanımda olduğu konumda kaynak kodu atlamak simgeleri değiştirme tanır.

İletişim kutusunda, aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|--------------------------|------------------------------------------|
|**Ad**|Simgenin adını görüntüler.<br/><br/>Daha fazla bilgi için [sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md).|
|**Değer**|Sembolün sayısal değerini görüntüler.<br/><br/>Daha fazla bilgi için [sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md).|
|**Kullanımda**|Bu onay kutusu seçildiğinde, simge bir veya daha fazla kaynak tarafından kullanılmakta olduğunu belirtir.<br/><br/>Kaynak veya kaynak listelenen **tarafından kullanılan** kutusu.|
|**Salt okunur sembolleri Göster**|Bu onay kutusu seçildiğinde, salt okunur kaynakları görüntüler.<br/><br/>Varsayılan olarak, **kaynak sembolü** iletişim kutusu, kaynak kod dosyanıza yalnızca değiştirilebilir kaynakları görüntüler ancak bu seçenek belirtilmişse, değiştirilebilir kaynakları kalın metin olarak görüntülenir ve salt okunur kaynaklar düz metin olarak görünür.|
|**Tarafından kullanılan**|Kaynak veya kaynak sembolleri listede seçilen sembolünü kullanarak görüntüler.<br/><br/>Belirli bir kaynak için düzenleyici taşımak için kaynağı seçin **tarafından kullanılan** seçin ve kutusunda **görünüm kullanımı**.|
|**Yeni**|Açılır **yeni sembol** adını tanımlamak sağlayan bir iletişim kutusu ve gerekirse, yeni bir sembolik kaynak tanımlayıcısı için bir değer.|
|**Değişiklik**|Açılır **sembol değiştirme** adı ya da bir sembolün değerini değiştirmek izin veren bir iletişim kutusu.<br/><br/>Simge bir denetim veya kaynağı için ise, simge yalnızca ilgili kaynak Düzenleyicisi'nden değiştirilebilir. Daha fazla bilgi için [yönetme sembolleri](../windows/changing-unassigned-symbols.md).|
|**Görünüm kullanımı**|Karşılık gelen kaynak Düzenleyicisi sembolü içeren kaynak açılır.|

## <a name="create-symbols"></a>Semboller oluşturma

### <a name="to-create-a-new-symbol"></a>Yeni bir sembolü oluşturmak için

1. İçinde **kaynak sembolleri** iletişim kutusunda **yeni**.

1. İçinde **adı** sembol adını yazın.

1. Atanan sembol değeri kabul edin veya yeni bir değer yazın **değer** kutusu.

1. Seçin **Tamam** yeni sembolü sembol listesine eklenecek.

> [!NOTE]
> Zaten bir sembol adı yazarsanız, bu ada sahip bir simge zaten tanımlandı belirten bir ileti kutusu görünür. Aynı ada sahip iki veya daha fazla sembolleri tanımlanamaz, ancak aynı sayısal değere sahip farklı bir simge tanımlayabilirsiniz.

## <a name="to-view-resource-symbols"></a>Kaynak sembolleri görüntülemek için

İçinde [kaynak görünümü](/windows/how-to-create-a-resource-script-file#create-resources), sağ tıklayın, *.rc* seçin ve dosya **kaynak sembolleri** kaynak sembolü tabloda görüntülemek için **kaynak sembolleri**iletişim kutusu.

> [!NOTE]
> Önceden tanımlanmış semboller görmek için **salt okunur sembolleri Göster** onay kutusu.

### <a name="to-open-the-resource-editor-for-a-given-symbol"></a>Belirli bir sembol için kaynak düzenleyicisini açmak için

Ne zaman, tarama sembolleri **kaynak sembolleri**, belirli bir sembolle nasıl kullanıldığı hakkında daha fazla bilgi isteyebilirsiniz. **Görünüm kullanımı** düğmesi, bu bilgileri almak için hızlı bir yol sağlar.

1. İçinde **kaynak sembolleri** iletişim kutusunda **adı** kutusunda, bir simge seçin.

1. İçinde **kullanılan tarafından** kutusunda, ilginizi çeken kaynak türü seçin.

1. Seçin **görünüm kullanımı** düğmesi.

   Kaynak uygun düzenleyici penceresinde görünür.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Tanımlayıcıları (Semboller)](../windows/symbols-resource-identifiers.md)<br/>
[Nasıl yapılır: Sembolleri Yönetme](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)<br/>