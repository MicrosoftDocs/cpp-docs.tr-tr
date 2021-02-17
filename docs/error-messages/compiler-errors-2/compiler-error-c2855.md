---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2855'
title: Derleyici hatası C2855
ms.date: 02/16/2021
f1_keywords:
- C2855
helpviewer_keywords:
- C2855
ms.openlocfilehash: cc26dbf92ea385ee05681e5fab8b5c4257c2b525
ms.sourcegitcommit: e99db7c3b5f25ece0e152165066c926751a7c2ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100643553"
---
# <a name="compiler-error-c2855"></a>Derleyici hatası C2855

> '*Option*' komut satırı seçeneği önceden derlenmiş üstbilgiyle tutarsız

Bu hata, bir komut satırı seçeneği önceden derlenmiş üstbilgiyi oluşturmak için kullanılan seçeneklerden farklıysa oluşur.

## <a name="remarks"></a>Açıklamalar

Bir derleyici seçeneğini değiştirdikten sonra artımlı bir derleme yaptığınızda hata C2855 oluşabilir. Tek tek kaynak dosyaları için belirli derleyici seçeneklerini ayarlarsanız de bu durum oluşabilir.

Bu hatayı çözmek için, belirtilen komut satırı seçeneğini kullanarak önceden derlenmiş üstbilgiyi yeniden oluşturun. Ön derlenmiş üstbilgiyi yeniden oluşturmak için ilişkili kaynak dosyayı oluşturun. Örneğin, bir Visual Studio şablonu tarafından oluşturulan projeler genellikle *`pch.cpp`* önceden derlenmiş üstbilgiyi oluşturmak için adlı bir kaynak dosya oluşturur. (Visual Studio 'nun eski sürümlerinde bu dosya adı verilir *`stdafx.cpp`* .) Diğer projelerde yeniden oluşturulacak kaynak dosya, [ `/Yc` (ön derlenmiş üstbilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) derleyici seçeneği kullanılarak oluşturulmuştur. Önceden derlenmiş üstbilgiye bir değişiklik yaptıktan sonra tüm projenizi yeniden oluşturmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[`/Y` (Önceden derlenmiş üst bilgiler)](../../build/reference/y-precompiled-headers.md)\
[Önceden derlenmiş üst bilgi dosyaları](../../build/creating-precompiled-header-files.md)
