---
title: Hata ayıklama ve listeleme satır içi derleme için | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 457402626edcdb2be05923aa33bbd26b1cab7137
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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