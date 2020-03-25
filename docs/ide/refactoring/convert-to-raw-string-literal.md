---
title: Ham dize değişmez değerine Dönüştür
ms.date: 11/16/2016
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
ms.openlocfilehash: 5636e00bfe8655d84fb2e4b64e0391324ab35d7d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171820"
---
# <a name="convert-to-raw-string-literal"></a>Ham dize değişmez değerine Dönüştür

**Ne:** Herhangi bir C++ dizeyi ham dize değişmez değerine açmanızı sağlar.

**Ne zaman:** Kaçış karakteri olan bir dizeniz var, kaçış karakterleri olarak işlenmemelidir.

**Neden:** İki kaçış karakteri de olabilir, ancak bu durum genellikle kafa karıştırıcı ve okunamaz dizeler için yol gösterir.  Ham dize değişmez değerlerini kullanmak dizelerin okunmasını çok daha kolay hale getirir.

**Oluşturulacağı**

1. Dönüştürülecek kaçış dizesinin üzerine metin veya fare imlecini yerleştir.

   ![Vurgulanan kod](images/stringliteral_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavyenizdeki**
     * **CTRL +** tuşlarına basın. **hızlı eylemleri ve yeniden düzenlemeler** menüsünü tetiklemek ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.
   * **Tığında**
     * Koda sağ tıklayın, **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü seçin ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.
     * Sol kenar boşluğunda görüntülenen ![ampul](images/bulb.png) simgesine tıklayın ve bağlam menüsünden **Ham dize değişmez değerine Dönüştür** ' ü seçin.

1. Dize hemen bir ham dize değişmez değerine dönüştürülür.

   ![Ham dize değişmez değeri](images/stringliteral_result.png)
