---
title: ANSI C uyumluluğu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- Ansi
dev_langs:
- C++
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fceb2681befa5ed9c8c82facb85442aed2d646
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023351"
---
# <a name="ansi-c-compliance"></a>ANSI C Uyumluluğu

Adlandırma Kuralı (örneğin, İşlevler, makroları, sabitleri, değişkenleri ve tür tanımları) çalışma zamanı sistemindeki tüm Microsoft'a özgü tanımlayıcıları için ANSI uyumlu olduğundan. Bu belgede, ANSI uyumlu olacak şekilde ANSI/ISO C standartlarını takip eden herhangi bir çalışma zamanı işlevini belirtilir. ANSI uyumlu uygulamalar, yalnızca bu ANSI uyumlu işlevler kullanmanız gerekir.

Microsoft'a özgü işlevleri ve genel değişkenler adları tek bir alt çizgi ile başlar. Bu adlar yalnızca yerel olarak, kodunuzun kapsamında geçersiz kılınabilir. Örneğin, Microsoft çalışma zamanı üst bilgi dosyaları eklediğinizde, adlı Microsoft'a özgü işlevi yerel olarak yine de kılabilirsiniz `_open` tarafından aynı ada sahip bir yerel değişken bildirme. Ancak, bu ad genel işlev veya genel değişkeni için kullanamazsınız.

Microsoft'a özgü makrolar ve bildirim sabitleri adları, bir büyük harf tarafından hemen ardından tek bir öncesinde alt çizgi veya iki alt çizgi ile başlar. Bu tanımlayıcılar kapsamını mutlaktır. Örneğin, Microsoft'a özgü tanımlayıcıyı kullanamazsınız **_UPPER** bu nedenle.

## <a name="see-also"></a>Ayrıca Bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)