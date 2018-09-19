---
title: Derleyici Hatası C2708 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2708
dev_langs:
- C++
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0accd68881cccad5e34530a6c157a4e8179b283
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111101"
---
# <a name="compiler-error-c2708"></a>Derleyici Hatası C2708

'identifier': Gerçek parametrenin bayt uzunluğu önceki çağrıdan veya başvurudan farklı farklıdır

A [__stdcall](../../cpp/stdcall.md) işlevi tarafından bir prototip öncesinde gerekir. Aksi halde, derleyici ilk çağrı işlevine bir prototip olarak yorumlar ve derleyici ile eşleşmeyen bir çağrı karşılaştığında bu hata oluşur.

Bu hatayı düzeltmek için bir işlev prototipi ekleyin.