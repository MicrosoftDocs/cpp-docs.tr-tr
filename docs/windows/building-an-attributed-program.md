---
title: Öznitelikli Program derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7909884a355ccad5e1bf9d18a38dd3e4690296ee
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42587513"
---
# <a name="building-an-attributed-program"></a>Öznitelikli Program Derleme

Kaynak kodunuza Visual C++ öznitelikleri geçirdikten sonra sizin için bir tür kitaplığı ve .idl dosyası oluşturmak için Visual C++ derleyicisi isteyebilirsiniz. Aşağıdaki bağlayıcı Yardım .tlb ve .idl dosyalarını derleme seçenekleri:

- [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)

- [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)

- [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)

Bazı projeler, birden çok bağımsız .idl dosyaları içerir. Bunlar, iki veya daha fazla .tlb dosyaları oluşturur ve isteğe bağlı olarak bunları kaynak bloğu içine bağlamak için kullanılır. Bu senaryo, Visual C++'da şu anda desteklenmiyor.

Ayrıca, Visual C++ bağlayıcı tüm öznitelik IDL ile ilgili bilgileri tek bir MIDL dosyasına çıkarır. İki tür kitaplıklarının tek bir projeden oluşturmak olanaksız olacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../windows/attributed-programming-concepts.md)