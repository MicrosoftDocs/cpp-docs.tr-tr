---
title: "Sabit değer ham dizesi Dönüştür | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c237f9042707654c913a24db916a82971603bb0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="convert-to-raw-string-literal"></a>Sabit değer ham dizesi Dönüştür
**Ne:** C++ ham dizeye herhangi bir dize sabit değeri kapatmanızı sağlar.

**Ne zaman:** Atlanan karakter olarak işlenen döndürmemelidir Atlanan karakterler içeren bir dize olması.

**Neden:** bu genellikle karmaşık ve okunamaz dizeleri müşteri adaylarına ancak çift kaçış karakterleri olabilir.  Ham dize değişmez değerleri kullanarak dizeleri okuma çok daha kolay hale getirir.

**Nasıl:**

1. Metin veya fare imleci dönüştürmek için kaçış karakterli dize yerleştirin.

   ![Vurgulanmış kodu](images/stringliteral_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ham dize sabit değeri için Dönüştür** ve bağlam menüsünden.
   * **Fare**
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ham dize sabit değeri için Dönüştür** ve bağlam menüsünden.
     * Tıklatın ![ampul](images/bulb.png) seçin ve sol kenar boşluğu içinde görünen simgesi **ham dize sabit değeri için dönüştürme** ve bağlam menüsünden.

1. Dize değişmez değer ham dizeye hemen dönüştürülür.  

   ![Ham dize sabit değeri sonucu](images/stringliteral_result.png)