---
title: CL seçenekleri (C++) - Visual Studio sırası
ms.date: 12/14/2018
f1_keywords:
- cl
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 93907265bed8141b5c63edd5e75d632e060351fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320948"
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası

Seçenekleri, CL komut satırında son gerçekleşmelidir/Link seçeneği dışında herhangi bir yerde görünebilir. Belirtilen seçeneklerle derleyici başlar [CL ortam değişkeninde](cl-environment-variables.md) ve komut satırı soldan sağa okur; bunları bulduğu sırada komut dosyaları işleme. Her seçeneğin komut satırında tüm dosyalar için geçerlidir. CL çakışan seçenekler karşılaşırsa, en sağdaki seçeneğini kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
