---
title: C Sıralama Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
ms.openlocfilehash: 13d6044269f60dc426a8b0b9b03463f387dfaa10
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152644"
---
# <a name="c-sequence-points"></a>C Sıralama Noktaları

Arasında ardışık "dizi noktaları bir nesnenin değerini değiştirilebilir yalnızca bir kez bir ifade tarafından". C dili, aşağıdaki dizi noktalarını tanımlar:

- Sol işlenen mantıksal- ve işleci (**&&**). Sol işleneni, mantıksal-işleci tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlayın. Sol işlenen yanlış (0) olarak değerlendirilirse diğer işlenen değerlendirilmez.

- Mantıksal OR işlecinin işleneni, sol (`||`). Mantıksal OR işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlayın. Sol işlenen true (sıfırdan farklı) olarak değerlendirilirse diğer işlenen değerlendirilmez.

- Virgül işlecinin sol işleneni. Virgül işlecinin sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlayın. Virgül işlecinin her iki işleneni de her zaman değerlendirilir. Bir işlev çağrısındaki virgül işlecinin bir değerlendirme sırasını garanti etmez unutmayın.

- İşlev çağrısı işleci. Bir işlev için tüm bağımsız değişkenler değerlendirilir ve işleve giriş önce tüm yan etkiler tamamlayın. Hiçbir bağımsız değişkenler arasından Değerlendirme sırasını belirtilir.

- Koşullu işlecin ilk işleneni. Koşullu işlecin ilk işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkiler tamamlayın.

- (Diğer bir deyişle, bir bildirim deyiminde başlatmanın sonu gibi başka bir ifade parçası olmayan bir ifade) bir tam başlatma ifadesinin sonu.

- Bir ifade deyimindeki ifade. İfade deyimleri, noktalı virgül tarafından izlenen isteğe bağlı bir ifade oluşur (**;**). İfade, yan etkileri için değerlendirilir ve bu değerlendirme izleyen bir dizi noktası yoktur.

- Seçim denetim ifadesi (**varsa** veya `switch`) deyimi. İfade tamamen değerlendirilir ve seçime bağlı kod yürütülmeden önce tüm yan etkiler tamamlayın.

- Denetim ifadesi, bir `while` veya **yapmak** deyimi. İfade tamamen değerlendirilir ve sonraki yinelemesinde yer alan herhangi bir deyim önce tüm yan etkiler tamamlamak `while` veya **yapmak** döngü yürütülür.

- Her üç ifadesinden bir **için** deyimi. İfade tamamen değerlendirilir ve sonraki yinelemesinde yer alan herhangi bir deyim önce tüm yan etkiler tamamlamak **için** döngü yürütülür.

- İfade bir `return` deyimi. İfade tamamen değerlendirilir ve denetim çağırma işlevine döndürmeden önce tüm yan etkiler tamamlayın.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Değerlendirme](../c-language/expression-evaluation-c.md)
