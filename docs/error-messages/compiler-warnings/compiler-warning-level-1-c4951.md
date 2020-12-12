---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4951'
title: Derleyici Uyarısı (düzey 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: effb1f5af0c406de002b5c0b8522e7c58a2424a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327961"
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951

> '*Function*', profil verileri toplandıktan sonra düzenlendi, işlev profili verileri kullanılmadı

Bir işlev bir giriş modülünde [/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)'e göre düzenlendi, bu nedenle profil verileri artık geçerli değil. Giriş modülü **/LTCG: pgınstrumafter** sonrasında yeniden derlenir ve **/LTCG: pgınstrumtıon** işlemi sırasında modülden farklı bir denetim akışı olan bir işlev (*işlev*) içeriyor.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için **/LTCG: PGıNSTRUMRUN**, tüm test çalıştırmalarını Yinele ve **/LTCG: pgoptimize**' i çalıştırın.

**/LTCG: PGOPTIMIZE** kullanılmışsa bu uyarı bir hata ile değiştirilmelidir.
