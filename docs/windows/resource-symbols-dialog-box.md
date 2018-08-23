---
title: Kaynak sembolleri iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourcesymbols
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box
- Resource Symbols dialog box
- Change Symbol dialog box
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc4c6a749a5e3ef1835d959e7803ac6b6f4435ec
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609825"
---
# <a name="resource-symbols-dialog-box"></a>Kaynak Sembolleri İletişim Kutusu

**Kaynak sembolleri** iletişim kutusu, yeni kaynak sembolleri eklemek için görüntülenen ya da sembol kullanımda olduğu konumda kaynak kodu atlamak simgeleri değiştirme tanır.

**Ad**  
Simgenin adını görüntüler. Daha fazla bilgi için [sembol adı kısıtlamaları](../windows/symbol-name-restrictions.md).

**Değer**  
Sembolün sayısal değerini görüntüler. Daha fazla bilgi için [sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md).

**Kullanımda**  
Bu onay kutusu seçildiğinde, simge bir veya daha fazla kaynak tarafından kullanılmakta olduğunu belirtir. Kaynak veya kaynak kutusu tarafından kullanılan listelenir.

**Salt okunur sembolleri Göster**  
Bu onay kutusu seçildiğinde, salt okunur kaynakları görüntüler. Varsayılan olarak, **kaynak sembolü** iletişim kutusu, kaynak kod dosyanıza yalnızca değiştirilebilir kaynakları görüntüler ancak bu seçenek belirtilmişse, değiştirilebilir kaynakları kalın metin olarak görüntülenir ve salt okunur kaynaklar düz metin olarak görünür.

**Tarafından kullanılan**  
Kaynak veya kaynak sembolleri listede seçilen sembolünü kullanarak görüntüler. Belirli bir kaynak için düzenleyici taşımak için kaynağı seçin **kullanılan tarafından** kutusuna ve tıklatın **görünüm kullanımı**. Daha fazla bilgi için [verilen bir sembol için kaynak Düzenleyicisini açma](../windows/opening-the-resource-editor-for-a-given-symbol.md).

**Yeni**  
Açılır **yeni sembol** iletişim kutusunda, ad tanımlamanıza olanak sağlar ve gerekirse, yeni bir sembolik kaynak tanımlayıcısı için bir değer. Daha fazla bilgi için [yeni semboller oluşturma](../windows/creating-new-symbols.md).

**Değişiklik**  
Açılır **sembol değiştirme** adı ya da bir sembolün değerini değiştirmek izin veren iletişim kutusu. Simge bir denetim veya kaynağı için ise, simge yalnızca ilgili kaynak Düzenleyicisi'nden değiştirilebilir. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).

**Görünüm kullanımı**  
Karşılık gelen kaynak Düzenleyicisi sembolü içeren kaynak açılır. Daha fazla bilgi için [verilen bir sembol için kaynak Düzenleyicisini açma](../windows/opening-the-resource-editor-for-a-given-symbol.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Sembollerini Görüntüleme](../windows/viewing-resource-symbols.md)