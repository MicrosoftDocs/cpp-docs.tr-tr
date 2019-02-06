---
title: Kaynak sembolleri (C++) görüntüleme
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.managing
- vc.editors.resourcesymbols
helpviewer_keywords:
- resources [C++], viewing
- resource symbols
- symbols [C++], viewing
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 4bcc06d9-7d36-486a-8a37-71da0541643c
ms.openlocfilehash: e61269261fc9172288f1edf58419009178c755d9
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55763979"
---
# <a name="viewing-resource-symbols"></a>Kaynak Sembolleri Görüntüleme

**Kaynak sembolleri** C++ iletişim kutusu, yeni kaynak sembolleri eklemek için görüntülenir ya da sembol kullanımda olduğu konumda kaynak kodu atlamak sembolleri değiştirme olanak tanır.

İletişim kutusunda, aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|---|---|
|**Ad**|Simgenin adını görüntüler. Daha fazla bilgi için [sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md).|
|**Değer**|Sembolün sayısal değerini görüntüler. Daha fazla bilgi için [sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md).|
|**Kullanımda**|Bu onay kutusu seçildiğinde, simge bir veya daha fazla kaynak tarafından kullanılmakta olduğunu belirtir. Kaynak veya kaynak kutusu tarafından kullanılan listelenir.|
|**Salt okunur sembolleri Göster**|Bu onay kutusu seçildiğinde, salt okunur kaynakları görüntüler. Varsayılan olarak, **kaynak sembolü** iletişim kutusu, kaynak kod dosyanıza yalnızca değiştirilebilir kaynakları görüntüler ancak bu seçenek belirtilmişse, değiştirilebilir kaynakları kalın metin olarak görüntülenir ve salt okunur kaynaklar düz metin olarak görünür.|
|**Tarafından kullanılan**|Kaynak veya kaynak sembolleri listede seçilen sembolünü kullanarak görüntüler. Belirli bir kaynak için düzenleyici taşımak için kaynağı seçin **kullanılan tarafından** kutusuna ve tıklatın **görünüm kullanımı**. Daha fazla bilgi için [verilen bir sembol için kaynak Düzenleyicisini açma](../windows/opening-the-resource-editor-for-a-given-symbol.md).|
|**Yeni**|Açılır **yeni sembol** iletişim kutusunda, ad tanımlamanıza olanak sağlar ve gerekirse, yeni bir sembolik kaynak tanımlayıcısı için bir değer. Daha fazla bilgi için [yeni semboller oluşturma](../windows/creating-new-symbols.md).|
|**Değişiklik**|Açılır **sembol değiştirme** adı ya da bir sembolün değerini değiştirmek izin veren iletişim kutusu. Simge bir denetim veya kaynağı için ise, simge yalnızca ilgili kaynak Düzenleyicisi'nden değiştirilebilir. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).|
|**Görünüm kullanımı**|Karşılık gelen kaynak Düzenleyicisi sembolü içeren kaynak açılır. Daha fazla bilgi için [verilen bir sembol için kaynak Düzenleyicisini açma](../windows/opening-the-resource-editor-for-a-given-symbol.md).|

## <a name="to-view-resource-symbols"></a>Kaynak sembolleri görüntülemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. Seçin **kaynak sembolleri** kaynak sembolü tabloda görüntülemek için kısayol menüsünden **kaynak sembolleri** iletişim kutusu.

   > [!NOTE]
   > Önceden tanımlanmış semboller görmek için **salt okunur sembolleri Göster** onay kutusu.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)