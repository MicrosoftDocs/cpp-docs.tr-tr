---
title: static depolama sınıfı tanımlayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1a58a8c7ab6eeb7d304d84cef15beb9046184fc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079498"
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı

İç düzeydeki ile bildirilen bir değişken **statik** depolama sınıfı tanımlayıcısı genel bir ömre sahiptir, ancak yalnızca blok içinde görülebilir içinde bildirildiği. Kullanarak sabit dizeleri için **statik** sık sık çağrılan işlevlerin başlatmada ek yükü azaltır çünkü yararlıdır.

## <a name="remarks"></a>Açıklamalar

Açıkça başlatılamadı, bir **statik** değişken, 0 için varsayılan olarak başlatılır. Bir işlev içinde **statik** ayrılacak depolama neden olur ve bir tanımı görev yapar. İç statik değişkenler yalnızca tek bir işleve görünür özel, kalıcı depolama sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[C Depolama Sınıfları](c-storage-classes.md)<br/>
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)