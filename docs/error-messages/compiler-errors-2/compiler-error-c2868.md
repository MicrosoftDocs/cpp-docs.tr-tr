---
title: Derleyici Hatası C2868 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2868
dev_langs:
- C++
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84465453ca7a1d76a9dd6b199232384c2ef9124b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2868"></a>Derleyici Hatası C2868  
  
> '*tanımlayıcısı*': kullanarak bildirimi için geçersiz sözdizimi; beklenen tam adı  
  
A [bildirimi kullanarak](../../cpp/using-declaration.md) gerektiren bir *tam adı*, kapsam işleci (`::`) tanımlayıcı adı ile biten bir dizi ad alanı, sınıf veya numaralandırma adları ayrılmış. Tek bir kapsam çözümü işleci genel ad alanından bir ad tanıtmak için kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek C2868 oluşturur ve ayrıca doğru kullanımını gösterir:  
  
```cpp  
// C2868.cpp  
class X {  
public:  
   int i;  
};  
  
class Y : X {  
public:  
   using X::i;   // OK  
};  
  
int main() {  
   using X;   // C2868  
}  
```