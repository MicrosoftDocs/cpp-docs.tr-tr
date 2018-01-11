---
title: "C sıralama noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: sequence points
ms.assetid: c84885a5-4336-4eba-a643-058df4249903
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5a9c874c0093b55c44f900e7eab06019d75cb930
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-sequence-points"></a>C Sıralama Noktaları
Ardışık arasında "bir nesnenin değeri değiştirilebilir yalnızca bir kez bir ifade sıralama noktaları". C dili aşağıdaki sıralama noktaları tanımlar:  
  
-   Sol işleneni mantıksal- ve işleci (**&&**). Sol işleneni mantıksal-işleci tamamen değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlayın. Sol işleneni (0) false hesaplanırsa başka işleneni değerlendirilmez.  
  
-   Sol işleneni mantıksal OR işleci (`||`). Mantıksal OR işleci sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlayın. Sol işleneni (sıfır) true olarak değerlendirilirse, diğer işleneni değerlendirilmez.  
  
-   Virgül işlecinin sol işleneni. Virgül işleci sol işleneni tamamen değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlayın. Virgül işlecinin her iki işleneni de her zaman değerlendirilir. Virgül işleci işlevi çağrısında Değerlendirme sırasını garanti etmez unutmayın.  
  
-   İşlev çağrısı işleci. Bir işlevin tüm bağımsız değişkenleri değerlendirilir ve işlev girişine önce tüm yan etkileri tamamlayın. Değerlendirme bağımsız değişkenleri arasında hiçbir sırasını belirtilir.  
  
-   Koşullu işlecin ilk işleneni. Koşullu işleç ilk işleneninin tamamen değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlayın.  
  
-   Bir tam başlatma ifadesi (bildirimi deyimi içinde bir başlatma sonuna gibi başka bir ifadenin bir parçası olmayan bir ifade) sonu.  
  
-   Bir ifade deyimindeki ifade. İfade deyimleri oluşur noktalı virgülle ayrılır ve ardından isteğe bağlı ifade (**;**). İfade için onun yan etkileri değerlendirilir ve bu değerlendirmesinin bir dizi noktası yok.  
  
-   Seçimdeki denetleme ifade (**varsa** veya `switch`) ifadesi. İfade tamamen değerlendirilir ve seçimini bağımlı kod yürütülmeden önce tüm yan etkileri tamamlayın.  
  
-   Kontrol eden bir ifade bir `while` veya **yapmak** deyimi. İfade tamamen değerlendirilir ve herhangi bir sonraki yinelemesini deyimlerinde önce tüm yan etkileri tamamlamak `while` veya **yapmak** döngü çalıştırılır.  
  
-   Her üç ifadelerin bir **için** deyimi. İfadeler tamamen değerlendirilir ve herhangi bir sonraki yinelemesini deyimlerinde önce tüm yan etkileri tamamlamak **için** döngü çalıştırılır.  
  
-   İfade bir `return` deyimi. İfade tamamen değerlendirilir ve denetim çağıran işleve döndürmeden önce tüm yan etkileri tamamlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme](../c-language/expression-evaluation-c.md)