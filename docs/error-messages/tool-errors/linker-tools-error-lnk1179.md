---
title: "Bağlayıcı araçları hatası LNK1179 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1179
dev_langs: C++
helpviewer_keywords: LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f026ef33452525f9e26da621517cadaeb57621e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1179"></a>Bağlayıcı Araçları Hatası LNK1179
geçersiz veya bozuk dosya: comdat'ı 'filename' Çoğalt  
  
 İki veya daha fazla COMDATs aynı ada sahip bir nesne modülü içerir.  
  
 Kullanarak bu hata oluşabilir [/H](../../build/reference/h-restrict-length-of-external-names.md), dış adların uzunluğunu sınırlar ve [/Gy](../../build/reference/gy-enable-function-level-linking.md), COMDATs işlevlerde paketler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda, `function1` ve `function2` ilk sekiz karakter aynıdır. İle derleme **/Gy** ve **/H8** bir bağlantı hatası oluşturur.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```