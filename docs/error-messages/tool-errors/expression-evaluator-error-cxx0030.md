---
title: İfade değerlendirici hatası CXX0030 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2921013d116b7d8f02e1e29380ca3cd14086b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102820"
---
# <a name="expression-evaluator-error-cxx0030"></a>İfade Değerlendirici Hatası CXX0030

ifade evaluatable değil

Hata Ayıklayıcı'nın ifade değerlendiricisi, yazıldığı gibi ifade için bir değer alınamadı. Olası nedenlerinden biri olan ifade programın adres alanı dışında bellek gösterir (örnek değer null işaretçisinin başvurusunun kaldırılması). Windows, programın adres alanının dışından bellek erişmesine izin vermez.

İfadeniz Değerlendirme sırasını denetlemek için parantez kullanılarak yeniden yazmak isteyebilirsiniz.

Bu hata için CAN0030 aynıdır.