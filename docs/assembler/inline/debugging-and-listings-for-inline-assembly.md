---
title: "Hata ayıklama ve listeleme satır içi derleme için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fea943c30d48ac122ae5d848306e4fe251f58da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Satır İçi Derleme için Hata Ayıklama ve Listeleme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Satır içi derleme kodu içeren programlar hata ayıklaması sahip bir kaynak düzey hata ayıklayıcı ile derleme yaparsanız [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği.  
  
 Hata ayıklayıcı içinde C veya C++ ve derleme dili satırlarında kesme noktaları ayarlayabilirsiniz. Karışık derleme ve kaynak modu etkinleştirirseniz, hem kaynak hem de bütünleştirilmiş kod artık hata ayıklayabildiğinize form görüntüleyebilirsiniz.  
  
 Tek bir satırda koyarak birden çok derleme yönergeleri veya kaynak dili ifadeleri hata ayıklama engel olabilir olduğunu unutmayın. Kaynak modunda, tek bir satırda ancak aynı satırda tek tek deyimleri kesme noktaları ayarlamak için hata ayıklayıcı kullanabilirsiniz. Aynı ilke uygulandığı bir `__asm` bloğu için tek bir mantıksal satır genişletir C makro olarak tanımlanır.  
  
 Bir karma kaynağı ve derleme ile listeleme oluşturursanız [/FAs](../../build/reference/fa-fa-listing-file.md) derleyici seçeneği, listenin her assembly dili satırının hem kaynak hem de derleme forms içerir. Makrolar listelerinde genişletilir değil, ancak derleme sırasında genişletilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında Bütünleştirilmiş Kod Dili Kullanma](../../assembler/inline/using-assembly-language-in-asm-blocks.md)