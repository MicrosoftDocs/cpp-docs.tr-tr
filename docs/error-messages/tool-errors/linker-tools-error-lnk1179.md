---
title: Bağlayıcı araçları hatası LNK1179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72a531397c3c101fbff937f293f772c5f6778523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300221"
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