---
title: 'Nasıl yapılır: semboller oluşturma (C++)'
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
ms.openlocfilehash: 008d2ab420034e628251c08222bf2e9f723deab1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504506"
---
# <a name="how-to-create-symbols-c"></a>Nasıl yapılır: semboller oluşturma (C++)

Yeni bir proje başladığınızda, atanacak kaynakları oluşturmadan önce ihtiyacınız olan sembol adlarını eşlemeyi uygun bulabilirsiniz.

> [!NOTE]
> Projeniz zaten bir. rc dosyası içermiyorsa bkz. [nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md).

**Kaynak sembolleri** iletişim kutusu, yeni kaynak sembolleri eklemenize, görüntülenen sembolleri değiştirmenize veya bir simgenin kullanımda olduğu kaynak kodundaki konuma atlamanızı sağlar.

İletişim kutusu aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|--------------------------|------------------------------------------|
|**Ad**|Simgenin adını görüntüler.<br/><br/>Daha fazla bilgi için bkz. [sembol adı kısıtlamaları](./changing-a-symbol-or-symbol-name-id.md).|
|**Değer**|Simgenin sayısal değerini görüntüler.<br/><br/>Daha fazla bilgi için bkz. [sembol değeri kısıtlamaları](./changing-a-symbol-or-symbol-name-id.md).|
|**Kullanımda**|Seçildiğinde, simgenin bir veya daha fazla kaynak tarafından kullanıldığını belirtir.<br/><br/>Kaynak veya kaynaklar, **tarafından kullanılan** kutusunda listelenir.|
|**Salt okunurdur sembolleri göster**|Seçildiğinde, salt okunurdur kaynakları görüntüler.<br/><br/>Varsayılan olarak, **kaynak sembolü** iletişim kutusu yalnızca kaynak betik dosyanızdaki değiştirilebilir kaynakları görüntüler, ancak bu seçenek belirlendiğinde, değiştirilebilir kaynaklar kalın metin ve salt okuma kaynakları düz metin halinde görünür.|
|**Kullanan**|Semboller listesinde seçilen simgeyi kullanarak kaynağı veya kaynakları görüntüler.<br/><br/>Belirli bir kaynak için düzenleyiciye gitmek üzere, **kullanılan** kutusunda kaynağı seçin ve **Görünüm kullan**' ı seçin.|
|**Yeni**|Adı ve gerekirse yeni bir sembolik kaynak tanımlayıcısı için bir değer tanımlamanızı sağlayan **yeni sembol** iletişim kutusunu açar.|
|**Değiştir**|Bir simgenin adını veya değerini değiştirmenize olanak sağlayan **sembolü Değiştir** iletişim kutusunu açar.<br/><br/>Sembol, kullanımda olan bir denetim veya kaynak için ise, simge yalnızca ilgili kaynak düzenleyiciden değiştirilebilir. Daha fazla bilgi için bkz. [sembolleri yönetme](./changing-a-symbol-or-symbol-name-id.md).|
|**Kullanımı görüntüle**|Karşılık gelen kaynak düzenleyicisinde sembolünü içeren kaynağı açar.|

## <a name="create-symbols"></a>Sembol oluştur

### <a name="to-create-a-new-symbol"></a>Yeni bir sembol oluşturmak için

1. **Kaynak sembolleri** Iletişim kutusunda **Yeni**' yi seçin.

1. **Ad** kutusuna bir sembol adı yazın.

1. Atanan sembol değerini kabul edin veya **değer** kutusuna yeni bir değer yazın.

1. Sembol listesine yeni sembolünü eklemek için **Tamam ' ı** seçin.

> [!NOTE]
> Zaten var olan bir sembol adı yazarsanız, bu ada sahip bir simgenin zaten tanımlandığını belirten bir ileti kutusu görünür. Aynı ada sahip iki veya daha fazla sembol tanımlayamazsınız, ancak aynı sayısal değere sahip farklı semboller tanımlayabilirsiniz.

## <a name="to-view-resource-symbols"></a>Kaynak sembolleri görüntülemek için

[Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), *. RC* dosyanıza sağ tıklayıp kaynak **sembolleri** ' ni seçerek kaynak **sembolleri** iletişim kutusunda bir kaynak sembol tablosu görüntüleyin.

> [!NOTE]
> Önceden tanımlanmış sembolleri görmek için **salt okunurdur sembolleri göster** onay kutusunu işaretleyin.

### <a name="to-open-the-resource-editor-for-a-given-symbol"></a>Belirli bir simgenin kaynak düzenleyicisini açmak için

**Kaynak sembollerinde**simgelere göz atarken, belirli bir simgenin nasıl kullanıldığı hakkında daha fazla bilgi isteyebilirsiniz. **Kullanımı görüntüle** düğmesi, bu bilgileri almanın hızlı bir yolunu sağlar.

1. **Ad** kutusunda **kaynak sembolleri** iletişim kutusunda bir sembol seçin.

1. **Kullanılan** kutusunda, ilgilendiğiniz kaynak türünü seçin.

1. **Kullanımı görüntüle** düğmesini seçin.

   Kaynak uygun düzenleyici penceresinde görünür.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak tanımlayıcıları (semboller)](../windows/symbols-resource-identifiers.md)<br/>
[Nasıl yapılır: sembolleri yönetme](../windows/changing-a-symbol-or-symbol-name-id.md)<br/>
[Önceden tanımlanmış sembol kimlikleri](../windows/predefined-symbol-ids.md)<br/>
