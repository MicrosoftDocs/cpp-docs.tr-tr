---
title: "MFC dışı DLL'ler: Genel bakış | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30a6fef31dee39cc6337b9b8b7dd3b66ee3adb67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702591"
---
# <a name="non-mfc-dlls-overview"></a>MFC Dışı DLL'ler: Genel Bakış

MFC olmayan DLL, MFC dahili olarak kullanmayan bir DLL modülüdür ve DLL'deki dışarı aktarılan işlevleri MFC veya MFC olmayan yürütülebilir dosyaları tarafından çağrılabilir. İşlevleri, genellikle standart C arabirimi kullanan MFC olmayan DLL'den dışarı aktarılır.

MFC olmayan DLL'leri hakkında daha fazla bilgi için [dinamik bağlantı kitaplıklarını](https://msdn.microsoft.com/library/windows/desktop/ms682589) Windows SDK.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [İzlenecek yol: Oluşturma ve bir dinamik bağlantı kitaplığı kullanma](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [DLL'den dışarı aktarma](../build/exporting-from-a-dll.md)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](../build/linking-an-executable-to-a-dll.md)

- [DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı DLL'leri: Genel Bakış](../build/extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca Bkz.

[DLL Türleri](../build/kinds-of-dlls.md)