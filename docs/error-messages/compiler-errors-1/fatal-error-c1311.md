---
title: Önemli hata C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: e57e4e0899a5f9d81e87a203b1b699cef0884f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203274"
---
# <a name="fatal-error-c1311"></a>Önemli hata C1311

COFF biçimi, ' var ' adresini bir adresin sayı baytına göre statik olarak başlatamıyor

Değeri, derleme zamanında bilinmeyen bir adres, türü Dört bayttan daha az depolama alanı olan bir değişkene statik olarak atanamaz.

Bu hata, başka bir durumda geçerli C++olan kodda ortaya çıkabilir.

Aşağıdaki örnekte, C1311 neden olabilecek bir durum gösterilmektedir.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
