---
title: Derleyici Uyarısı (düzey 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: d94347df17bac01334cfd85c2bd9f6c8a98b5fc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174602"
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951

> '*Function*', profil verileri toplandıktan sonra düzenlendi, işlev profili verileri kullanılmadı

Bir işlev bir giriş modülünde [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)'e göre düzenlendi, bu nedenle profil verileri artık geçerli değil. Giriş modülü **/LTCG: pgınstrumafter** sonrasında yeniden derlenir ve **/LTCG: pgınstrumtıon** işlemi sırasında modülden farklı bir denetim akışı olan bir işlev (*işlev*) içeriyor.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için **/LTCG: PGıNSTRUMRUN**, tüm test çalıştırmalarını Yinele ve **/LTCG: pgoptimize**' i çalıştırın.

**/LTCG: PGOPTIMIZE** kullanılmışsa bu uyarı bir hata ile değiştirilmelidir.
