---
title: Önemli Hata C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 056db975fecef4e101dbbba7e2084236489498c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202871"
---
# <a name="fatal-error-c1853"></a>Önemli Hata C1853

> '*filename*' ön derlenmiş üstbilgi dosyası derleyicinin önceki bir sürümünden veya ön derlenmiş üstbilgi C++ ve C 'den kullanıyorsunuz (veya tersi)

Olası nedenler:

- Ön derlenmiş üstbilgi önceki bir derleyici sürümü ile derlendi. Üstbilgiyi geçerli derleyiciyle yeniden derleme yapmayı deneyin.

- Ön derlenmiş üst bilgi C++ ve c 'den kullanıyorsunuz. [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneklerinden birini belirterek veya kaynak dosyanın sonekini "C" olarak değiştirerek c ile kullanmak için üstbilgiyi yeniden derleme. Daha fazla bilgi için bkz. [önceden derleme kodu Için Iki seçenek](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code).
