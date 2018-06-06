---
title: Sabit değer ham dizesi Dönüştür | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b98825719e7b3c0d8eb760a2ec50644b5eddd54e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328415"
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