---
description: 'Daha fazla bilgi edinin: önemli hata C1311'
title: Önemli hata C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: d6049bfedd01be02e8b3f26163fe062e9023bd78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177750"
---
# <a name="fatal-error-c1311"></a>Önemli hata C1311

COFF biçimi, ' var ' adresini bir adresin sayı baytına göre statik olarak başlatamıyor

Değeri, derleme zamanında bilinmeyen bir adres, türü Dört bayttan daha az depolama alanı olan bir değişkene statik olarak atanamaz.

Bu hata, aksi durumda geçerli C++ olan kodda ortaya çıkabilir.

Aşağıdaki örnekte, C1311 neden olabilecek bir durum gösterilmektedir.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
