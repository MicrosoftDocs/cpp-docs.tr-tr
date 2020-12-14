---
description: 'Daha fazla bilgi edinin: CL seçenekleri sırası'
title: CL seçenekleri sırası (C++)-Visual Studio
ms.date: 12/14/2018
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
ms.openlocfilehash: bc0290164ff40cf45d8d0a1e9f07e683e408c251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226421"
---
# <a name="order-of-cl-options"></a>CL Seçenekleri Sırası

Seçenekler, en son oluşması gereken/Link seçeneği dışında, CL komut satırında herhangi bir yerde görünebilir. Derleyici [CL ortam değişkeninde](cl-environment-variables.md) belirtilen seçeneklerle başlar ve ardından komut satırını soldan sağa okur ve komut dosyalarını, karşılaştığı sırada işleme. Her seçenek komut satırındaki tüm dosyalar için geçerlidir. CL çakışan seçeneklerle karşılaşırsa, en sağdaki seçeneği kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
