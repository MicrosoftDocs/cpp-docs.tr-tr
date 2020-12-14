---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1 ve 4) C4115'
title: Derleyici Uyarısı (düzey 1 ve 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: f41dcdf16d541151384d50d004a55d6e1993ece0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234506"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Derleyici Uyarısı (düzey 1 ve 4) C4115

' Type ': parantez içinde adlandırılmış tür tanımı

Verilen sembol bir parantez, birleşim veya numaralandırılmış türü parantez içinde bir ifade içinde tanımlamak için kullanılır. Tanımın kapsamı beklenmeyen bir durum olabilir.

C işlev çağrısında, tanım genel kapsama sahip. C++ çağrısında, tanım çağrılan işlevle aynı kapsama sahiptir.

Bu uyarı, parantez içinde olmayan deyimlerden (örneğin Prototiplerde) de neden olabilir.

Bu, ANSI uyumluluğu (/Za) altında derlenen C++ programları ve C programlarıyla bir düzey 1 uyarıdır. Aksi takdirde, düzey 3 ' dir.
