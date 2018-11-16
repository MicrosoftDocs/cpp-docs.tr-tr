---
title: Saf sanalları Uygula
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: 59e4519f57a1d9bd9ba1cee1ed6ae41bea785a9f
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51692677"
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
