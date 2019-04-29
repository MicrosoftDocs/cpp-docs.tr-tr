---
title: Ham dize sabit değerine Dönüştür
ms.date: 11/16/2016
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
ms.openlocfilehash: bf492e6796b9d2342b5952abb093bddd5ede114b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349439"
---
# <a name="convert-to-raw-string-literal"></a>Ham dize sabit değerine Dönüştür

**Ne:** Herhangi bir dize özelliğini sağlar bir C++ ham dize sabit değeri.

**ne zaman:** Kaçan karakter olarak işlenen olmamalıdır atlatmalı karakterler içeren bir dize var.

**Neden:** Bu genellikle karmaşık ve okunamaz dizeleri müşteri adaylarını haricinde çift kaçış karakterleri yapabilirsiniz.  Ham dize değişmez değerleri kullanarak dizeler okumak çok daha kolay hale getirir.

**Nasıl:**

1. Dönüştürülecek kaçan dize içinde metin veya fare imleci yerleştirin.

   ![Vurgulanmış kodu](images/stringliteral_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **ham dize sabit değeri için dönüştürme** bağlam menüsünden.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **ham dize sabit değeri için dönüştürme** bağlam menüsünden.
     * Tıklayın ![ampul](images/bulb.png) seçin ve sol kenar boşluğu içinde görünen simge **ham dize sabit değeri için dönüştürme** bağlam menüsünden.

1. Dizeyi, ham dize değişmez değeri içinde hemen dönüştürülür.

   ![Ham dize değişmez değer sonucu](images/stringliteral_result.png)