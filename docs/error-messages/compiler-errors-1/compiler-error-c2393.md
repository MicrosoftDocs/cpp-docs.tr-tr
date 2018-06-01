---
title: Derleyici Hatası C2393 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 057537c8efcf6e827d9ac9aaf36c0eace6d24156
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704036"
---
# <a name="compiler-error-c2393"></a>Derleyici Hatası C2393

> '*simgesi*': appdomain başına simgesi kesimdeki ayrılamıyor '*segment*'

## <a name="remarks"></a>Açıklamalar

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Kullanımını [appdomain](../../cpp/appdomain.md) değişkenleri gelir ile derlediğiniz **/CLR: pure** veya **/CLR: safe**, ve güvenli veya saf görüntü veri bölümleri içeremez.

Bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2393 oluşturur. Bu sorunu gidermek için veri kesimi oluşturmayın.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```