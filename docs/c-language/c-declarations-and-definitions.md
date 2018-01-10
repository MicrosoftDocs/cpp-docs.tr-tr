---
title: "C tanımları ve bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 526a7bb902374fb3df936d5ac81cf602e1871a4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-declarations-and-definitions"></a>C Tanımları ve Bildirimleri
Bir "bildirim" belirli bir değişken, işlev veya tür ve öznitelikleri arasında bir ilişki kurar. [Bildirimlere genel bakış](../c-language/overview-of-declarations.md) ANSI sözdizimi verir `declaration` nonterminal. Bir bildirim, bir tanımlayıcıya nereden ve ne zaman erişilebileceğini de belirtir (bir tanımlayıcının "bağlantısı"). Bkz: [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md) bağlantı hakkında bilgi için.  
  
 Bir değişkenin "tanımı" bildirimle aynı ilişkileri kurar, ancak depolamanın değişken için ayrılmasına da neden olur.  
  
 Örneğin, `main`, `find` ve `count` işlevleri ve `var` ve `val` değişkenleri aşağıdaki sırayla bir kaynak dosyasında tanımlanır:  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 `var` ve `val` değişkenleri `find` ve `count` işlevlerinde kullanılır; başka bildirime gerek yoktur. Ancak bu adlar `main`'de görünmez (erişilemez).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Dosyalar ve Kaynak Programlar](../c-language/source-files-and-source-programs.md)