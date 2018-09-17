---
title: Bir uygulamaya aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e88d34ce685e22e561683cc33db25997650ed7fd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718397"
---
# <a name="importing-into-an-application"></a>Bir Uygulamaya Aktarma

İki yöntemi kullanarak bir uygulamaya işlevleri içeri aktarabilirsiniz:

- Anahtar kelimeler kullanmanız **__declspec(dllimport)** ana uygulamadaki bir işlev tanımı

- Modül tanım (.def) dosyası ile birlikte kullanmak **__declspec(dllimport)**

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [__Declspec(dllimport) kullanarak bir uygulamaya'na aktarma](../build/importing-into-an-application-using-declspec-dllimport.md)

- [__Declspec(dllimport) kullanarak işlev çağrılarını içeri aktarma](../build/importing-function-calls-using-declspec-dllimport.md)

- [__Declspec(dllimport) kullanarak veriyi içeri aktarma](../build/importing-data-using-declspec-dllimport.md)

- [DEF dosyalarını kullanarak içeri aktarma](../build/importing-using-def-files.md)

## <a name="see-also"></a>Ayrıca Bkz.

[İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)