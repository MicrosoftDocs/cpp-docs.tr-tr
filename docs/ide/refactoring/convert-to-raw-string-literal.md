---
description: 'Daha fazla bilgi edinin: ham dize değişmez değerine Dönüştür'
title: Ham dize değişmez değerine Dönüştür
ms.date: 11/16/2016
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
ms.openlocfilehash: f83cb955bc2b30957306e1467a2d353377d5f33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185563"
---
# <a name="convert-to-raw-string-literal"></a>Ham dize değişmez değerine Dönüştür

**Ne:** Bir dizeyi C++ ham dize değişmez değerine açmanızı sağlar.

**Ne zaman:** Kaçış karakteri olan bir dizeniz var, kaçış karakterleri olarak işlenmemelidir.

**Neden:** İki kaçış karakteri de olabilir, ancak bu durum genellikle kafa karıştırıcı ve okunamaz dizeler için yol gösterir.  Ham dize değişmez değerlerini kullanmak dizelerin okunmasını çok daha kolay hale getirir.

**Oluşturulacağı**

1. Dönüştürülecek kaçış dizesinin üzerine metin veya fare imlecini yerleştir.

   ![Vurgulanan kod](images/stringliteral_highlight.png)

1. Sonra, aşağıdakilerden birini yapın:
   * **Klavye**
     * **CTRL +** tuşlarına basın. **hızlı eylemleri ve yeniden düzenlemeler** menüsünü tetiklemek ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.
   * **Fare**
     * Koda sağ tıklayın, **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü seçin ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.
     * ![ ](images/bulb.png) Sol kenar boşluğunda görüntülenen ampul simgesine tıklayın ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.

1. Dize hemen bir ham dize değişmez değerine dönüştürülür.

   ![Ham dize değişmez değeri](images/stringliteral_result.png)
