---
title: C Sıralama Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
ms.openlocfilehash: 0147f51063127cb26ce8caf70bc46eadc87b8d3e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226522"
---
# <a name="c-sequence-points"></a>C Sıralama Noktaları

Ardışık "dizi noktaları" bir nesnenin değeri, bir ifade tarafından yalnızca bir kez değiştirilebilir. C dili aşağıdaki sıra noktalarını tanımlar:

- Mantıksal AND işlecinin sol işleneni ( **&&** ). Mantıksal AND işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Sol işlenen yanlış (0) olarak değerlendirilirse, diğer işlenen değerlendirilmez.

- Mantıksal OR işlecinin sol işleneni ( `||` ). Mantıksal OR işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Sol işlenen true (sıfır dışında) olarak değerlendirilirse, diğer işlenen değerlendirilmez.

- Virgül işlecinin sol işleneni. Virgül işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Virgül işlecinin her iki işleneni de her zaman değerlendirilir. Bir işlev çağrısındaki virgül işlecinin değerlendirme sırasını garanti vermediğini unutmayın.

- İşlev çağrısı işleci. İşleve yapılan tüm bağımsız değişkenler değerlendirilir ve işleve girişte önce tüm yan etkiler tamamlanır. Bağımsız değişkenler arasında değerlendirme sırası belirtilmedi.

- Koşullu işlecin ilk işleneni. Koşullu işlecin ilk işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır.

- Tam başlatma ifadesinin sonu (diğer bir deyişle, bir bildirim deyiminde başlatmanın sonu gibi başka bir ifadenin parçası olmayan bir ifadedir).

- Bir ifade deyimindeki ifade. Expression deyimleri, bir isteğe bağlı ifadeden sonra noktalı virgül (**;**) içerir. İfade, yan etkileri için değerlendirilir ve bu değerlendirmeyi izleyen bir sıra noktası vardır.

- Seçim ( **`if`** veya **`switch`** ) deyimindeki denetim ifadesi. İfade tamamen değerlendirilir ve seçime bağlı kod yürütülmeden önce tüm yan etkiler tamamlanır.

- **`while`** Or deyiminin denetim ifadesi **`do`** . İfade tamamen değerlendirilir ve veya döngüsünün bir sonraki yinelemesinde herhangi bir deyim yürütülmeden önce tüm yan etkiler tamamlanır **`while`** **`do`** .

- Bir deyimin üç ifadesinin her biri **`for`** . İfade tamamen değerlendirilir ve döngünün bir sonraki yinelemesinde hiçbir deyim yürütülmeden önce tüm yan etkiler tamamlanır **`for`** .

- **`return`** Deyimdeki ifade. İfade tamamen değerlendirilir ve denetim, çağırma işlevine dönüşmeden önce tüm yan etkiler tamamlanır.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Değerlendirme](../c-language/expression-evaluation-c.md)
