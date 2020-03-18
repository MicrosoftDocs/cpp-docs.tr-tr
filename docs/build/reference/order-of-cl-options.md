---
title: CL seçenekleri sırası (C++)-Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: 6c57a68dd15d82a9d6a01bfe145374bda6eb1510
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439204"
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası

Seçenekler, en son oluşması gereken/Link seçeneği dışında, CL komut satırında herhangi bir yerde görünebilir. Derleyici [CL ortam değişkeninde](cl-environment-variables.md) belirtilen seçeneklerle başlar ve ardından komut satırını soldan sağa okur ve komut dosyalarını, karşılaştığı sırada işleme. Her seçenek komut satırındaki tüm dosyalar için geçerlidir. CL çakışan seçeneklerle karşılaşırsa, en sağdaki seçeneği kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
