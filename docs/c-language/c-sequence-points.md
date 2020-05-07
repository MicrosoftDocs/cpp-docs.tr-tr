---
title: C Sıralama Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
ms.openlocfilehash: 13d6044269f60dc426a8b0b9b03463f387dfaa10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313343"
---
# <a name="c-sequence-points"></a>C Sıralama Noktaları

Ardışık "dizi noktaları" bir nesnenin değeri, bir ifade tarafından yalnızca bir kez değiştirilebilir. C dili aşağıdaki sıra noktalarını tanımlar:

- Mantıksal AND işlecinin sol işleneni (**&&**). Mantıksal AND işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Sol işlenen yanlış (0) olarak değerlendirilirse, diğer işlenen değerlendirilmez.

- Mantıksal OR işlecinin sol işleneni (`||`). Mantıksal OR işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Sol işlenen true (sıfır dışında) olarak değerlendirilirse, diğer işlenen değerlendirilmez.

- Virgül işlecinin sol işleneni. Virgül işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır. Virgül işlecinin her iki işleneni de her zaman değerlendirilir. Bir işlev çağrısındaki virgül işlecinin değerlendirme sırasını garanti vermediğini unutmayın.

- İşlev çağrısı işleci. İşleve yapılan tüm bağımsız değişkenler değerlendirilir ve işleve girişte önce tüm yan etkiler tamamlanır. Bağımsız değişkenler arasında değerlendirme sırası belirtilmedi.

- Koşullu işlecin ilk işleneni. Koşullu işlecin ilk işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlanır.

- Tam başlatma ifadesinin sonu (diğer bir deyişle, bir bildirim deyiminde başlatmanın sonu gibi başka bir ifadenin parçası olmayan bir ifadedir).

- Bir ifade deyimindeki ifade. Expression deyimleri, bir isteğe bağlı ifadeden sonra noktalı virgül (**;**) içerir. İfade, yan etkileri için değerlendirilir ve bu değerlendirmeyi izleyen bir sıra noktası vardır.

- Seçim (**if** veya `switch`) deyimi içindeki denetim ifadesi. İfade tamamen değerlendirilir ve seçime bağlı kod yürütülmeden önce tüm yan etkiler tamamlanır.

- `while` Or **Do** deyiminin denetim ifadesi. İfade tamamen değerlendirilir ve `while` ya da **Do** döngüsünün bir sonraki yinelemesinde herhangi bir deyim yürütülmeden önce tüm yan etkiler tamamlanır.

- **For** ifadesinin üç ifadesinin her biri. İfadeler tamamen değerlendirilir ve **for** döngüsünün bir sonraki yinelemesinde hiçbir deyim yürütülmeden önce tüm yan etkiler tamamlanır.

- `return` Deyimdeki ifade. İfade tamamen değerlendirilir ve denetim, çağırma işlevine dönüşmeden önce tüm yan etkiler tamamlanır.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Değerlendirme](../c-language/expression-evaluation-c.md)
