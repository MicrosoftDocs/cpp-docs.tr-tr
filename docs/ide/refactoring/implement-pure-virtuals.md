---
description: 'Daha fazla bilgi edinin: saf sanalları Uygula'
title: Saf sanalları Uygula
ms.date: 11/16/2016
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
ms.openlocfilehash: b35ebba556ed9bae6ded649caca000b7d3554480
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318760"
---
# <a name="implement-pure-virtuals"></a>Saf sanalları Uygula

**Ne:** Bir sınıftaki tüm saf sanal yöntemleri uygulamak için gereken kodu hemen üretmenizi sağlar.

**Ne zaman:** Saf sanal işlevler içeren bir sınıftan devralma yapmak istiyorsunuz.

**Neden:** Tüm saf sanal işlevleri tek tek el ile uygulayabilirsiniz, ancak bu özellik tüm yöntem imzalarını otomatik olarak oluşturur.

**Oluşturulacağı**

1. Metin veya fare imlecinizi, temel sınıfın saf sanal işlevlerini uygulamak istediğiniz sınıfın üzerine yerleştirin.

   ![Vurgulanan kod](images/virtuals_highlight.png)

1. Sonra, aşağıdakilerden birini yapın:
   * **Klavye**
     * **CTRL +** tuşlarına basın. **hızlı eylemleri ve yeniden düzenlemeler** menüsünü tetiklemek ve bağlam menüsünden **'*ClassName*' sınıfı Için tüm saf sanalları Uygula '** yı seçin, burada *ClassName* Seçili sınıfın adıdır.
   * **Fare**
     * Sağ tıklayın ve **Hızlı Eylemler ve yeniden düzenlemeler** menüsünü seçin ve bağlam menüsünden **'*ClassName*' sınıfı Için tüm saf sanalları Uygula '** yı seçin, burada *ClassName* Seçili sınıfın adıdır.

1. Saf sanal yöntem imzaları otomatik olarak oluşturulur ve uygulanmak üzere hazırlanacaktır.

   ![Saf Sanallar sonucunu Uygula](images/virtuals_result.png)
