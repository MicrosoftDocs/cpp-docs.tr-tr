---
title: Derleyici Hatası C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a128613cabb201142c29b833959924dbf8a6e0ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460079"
---
# <a name="compiler-error-c2708"></a>Derleyici Hatası C2708

'identifier': Gerçek parametrenin bayt uzunluğu önceki çağrıdan veya başvurudan farklı farklıdır

A [__stdcall](../../cpp/stdcall.md) işlevi tarafından bir prototip öncesinde gerekir. Aksi halde, derleyici ilk çağrı işlevine bir prototip olarak yorumlar ve derleyici ile eşleşmeyen bir çağrı karşılaştığında bu hata oluşur.

Bu hatayı düzeltmek için bir işlev prototipi ekleyin.