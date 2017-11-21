---
title: "Derleyici Hatası C2868 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2868
dev_langs: C++
helpviewer_keywords: C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 62c8ea961db2547976e39a8873542a9f85dc4be7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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