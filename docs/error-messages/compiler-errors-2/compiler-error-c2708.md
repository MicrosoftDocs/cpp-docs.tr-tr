---
title: Derleyici Hatası C2708
ms.date: 11/04/2016
f1_keywords:
- C2708
helpviewer_keywords:
- C2708
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
ms.openlocfilehash: a128613cabb201142c29b833959924dbf8a6e0ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160964"
---
# <a name="compiler-error-c2708"></a>Derleyici Hatası C2708

'identifier': Gerçek parametrenin bayt uzunluğu önceki çağrıdan veya başvurudan farklı farklıdır

A [__stdcall](../../cpp/stdcall.md) işlevi tarafından bir prototip öncesinde gerekir. Aksi halde, derleyici ilk çağrı işlevine bir prototip olarak yorumlar ve derleyici ile eşleşmeyen bir çağrı karşılaştığında bu hata oluşur.

Bu hatayı düzeltmek için bir işlev prototipi ekleyin.