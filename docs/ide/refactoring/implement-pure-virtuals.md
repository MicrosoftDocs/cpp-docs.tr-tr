---
title: Saf sanalları Uygula
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: e693fdc17057d3800053bf5a7bad64ec441bcc3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614909"
---
# <a name="implement-pure-virtuals"></a>Saf sanalları Uygula
**Ne:** hemen bir sınıfta tüm saf sanal yöntemleri uygulamak için gereken kodu oluşturmanıza olanak tanır.

**Ne zaman:** saf sanal işlevler içeren bir sınıfından devralmasına izin istiyor.

**Neden:** bu özellik otomatik olarak tüm yöntem imzaları oluşturur ancak tüm saf sanal işlevler birer birer el ile uygulayabilirsiniz.

**Nasıl:**

1. Sınıf temel sınıfın saf sanal işlevler uygulamak istediğiniz metin veya fare imleci yerleştirin.

   ![Vurgulanmış kodu](images/virtuals_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **sınıf için tüm saf sanalları Uygula*ClassName*'** bağlam menüsünden burada  *ClassName* seçilen bir sınıf adıdır.
   * **Fare**
     * Sağ tıklayıp **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **sınıf için tüm saf sanalları Uygula*ClassName*'** bağlam menüsünden burada  *ClassName* seçilen bir sınıf adıdır.

1. Saf sanal yöntem imzaları, otomatik olarak oluşturulan, uygulanmak hazır olacaktır.

   ![Saf sanalları neden](images/virtuals_result.png)
