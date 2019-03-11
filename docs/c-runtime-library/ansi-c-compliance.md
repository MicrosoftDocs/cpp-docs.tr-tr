---
title: ANSI C Uyumluluğu
ms.date: 11/04/2016
f1_keywords:
- Ansi
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
ms.openlocfilehash: 7a4462e84ec01bd236849c6aed024b636b315243
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742816"
---
# <a name="ansi-c-compliance"></a>ANSI C Uyumluluğu

Adlandırma Kuralı (örneğin, İşlevler, makroları, sabitleri, değişkenleri ve tür tanımları) çalışma zamanı sistemindeki tüm Microsoft'a özgü tanımlayıcıları için ANSI uyumlu olduğundan. Bu belgede, ANSI uyumlu olacak şekilde ANSI/ISO C standartlarını takip eden herhangi bir çalışma zamanı işlevini belirtilir. ANSI uyumlu uygulamalar, yalnızca bu ANSI uyumlu işlevler kullanmanız gerekir.

Microsoft'a özgü işlevleri ve genel değişkenler adları tek bir alt çizgi ile başlar. Bu adlar yalnızca yerel olarak, kodunuzun kapsamında geçersiz kılınabilir. Örneğin, Microsoft çalışma zamanı üst bilgi dosyaları eklediğinizde, adlı Microsoft'a özgü işlevi yerel olarak yine de kılabilirsiniz `_open` tarafından aynı ada sahip bir yerel değişken bildirme. Ancak, bu ad genel işlev veya genel değişkeni için kullanamazsınız.

Microsoft'a özgü makrolar ve bildirim sabitleri adları, bir büyük harf tarafından hemen ardından tek bir öncesinde alt çizgi veya iki alt çizgi ile başlar. Bu tanımlayıcılar kapsamını mutlaktır. Örneğin, Microsoft'a özgü tanımlayıcıyı kullanamazsınız **_UPPER** bu nedenle.

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
