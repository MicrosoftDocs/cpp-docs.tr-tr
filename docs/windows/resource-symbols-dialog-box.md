---
title: Kaynak sembolleri iletişim kutusu (C++) | Microsoft Docs
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
- New Symbol dialog box [C++]
- Resource Symbols dialog box [C++]
- Change Symbol dialog box [C++]
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 064fb9adce8b41c13709819f7ce0b7c515fea12a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313175"
---
# <a name="resource-symbols-dialog-box-c"></a>Kaynak sembolleri iletişim kutusu (C++)

**Kaynak sembolleri** C++ iletişim kutusu, yeni kaynak sembolleri eklemek için görüntülenir ya da sembol kullanımda olduğu konumda kaynak kodu atlamak sembolleri değiştirme olanak tanır.

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