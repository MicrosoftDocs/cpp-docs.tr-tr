---
title: "işlem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: process_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d7eaeb62f3d8231d7b1a5bca503cd355f7a7aca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="process"></a>process
Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu öncelikle ile derleme yapılırken kullanılacak yöneliktir **/CLR: pure**, çünkü altında **/CLR: pure** genel ve statik değişkenlerdir varsayılan uygulama etki alanı başına. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. İle derleme yapılırken **/CLR**, genel ve statik değişkenlerdir varsayılan işlem başına (kullanmasına gerek kalmamasını `__declspec(process)`.  
  
 Yalnızca bir genel değişken, bir statik üye değişkeni veya özgün türün statik bir yerel değişkeni `__declspec(process)` ile işaretlenebilir.  
  
 İle derleme yapılırken **/CLR: pure**, işlem başına işaretlenen değişkenler de bildirilmelidir olarak `const`. Bu, işleme göre değişkenlerinin bir uygulama etki alanında değiştirilmemesini sağlar ve başka bir uygulama etki alanında beklenmeyen sonuçlar verir. Birincil kullanılmaya `__declspec(process)` derleme zamanı başlatma genel değişkeni, statik üye değişkeni ya da statik yerel değişken altında etkinleştirmektir **/CLR: pure**.  
  
 `process`ile derleme yapılırken yalnızca geçerlidir [/CLR](../build/reference/clr-common-language-runtime-compilation.md) veya **/CLR: pure** ve ile derleme yapılırken geçersiz **/CLR: safe**.  
  
 Her uygulama etki genel değişkeni kendi kopyasına sahip olmasını istiyorsanız, kullanmak [appdomain](../cpp/appdomain.md).  
  
 Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)