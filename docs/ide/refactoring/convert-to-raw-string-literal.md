---
title: Ham dize sabit değerine Dönüştür
ms.date: 11/16/2016
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
ms.openlocfilehash: bf492e6796b9d2342b5952abb093bddd5ede114b
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692608"
---
# <a name="convert-to-raw-string-literal"></a>Ham dize sabit değerine Dönüştür

**Ne:** herhangi bir dize bir C++ ham dize sabit değeri kapatmanızı sağlar.

**Ne zaman:** atlatmalı karakterler olarak işlenen olmamalıdır atlatmalı karakterler içeren bir dize olması.

**Neden:** çift kaçış karakterleri, ancak bu genellikle karmaşık ve okunamaz dizelere müşteri adayları yüklenemedi.  Ham dize değişmez değerleri kullanarak dizeler okumak çok daha kolay hale getirir.

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