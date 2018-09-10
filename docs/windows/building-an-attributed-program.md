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
- tlb files [C++]
- MIDL
- MIDL, linker output
- IDL files [C++]
- building type libraries and .idl files
- .tlb files [C++]
- .idl files [C++]
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2fc148478433106eabdb2bc57ef7bb6c91d13601
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315300"
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