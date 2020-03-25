---
title: Derleyici Uyarısı (düzey 1 ve 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: 7e39e8c837d94776a804da2bf38643b453edb949
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198048"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Derleyici Uyarısı (düzey 1 ve 4) C4115

' Type ': parantez içinde adlandırılmış tür tanımı

Verilen sembol bir parantez, birleşim veya numaralandırılmış türü parantez içinde bir ifade içinde tanımlamak için kullanılır. Tanımın kapsamı beklenmeyen bir durum olabilir.

C işlev çağrısında, tanım genel kapsama sahip. Bir C++ çağrıda, tanım çağrılan işlevle aynı kapsama sahip.

Bu uyarı, parantez içinde olmayan deyimlerden (örneğin Prototiplerde) de neden olabilir.

Bu, ANSI uyumluluğu (/Za) C++ altında derlenen programlar ve C programlarıyla bir düzey 1 uyarıdır. Aksi takdirde, düzey 3 ' dir.
