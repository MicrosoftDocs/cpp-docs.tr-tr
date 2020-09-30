---
title: ANSI C Uyumluluğu
description: ANSI C uyumluluğu için Microsoft C çalışma zamanı adlandırma kurallarına genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
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
ms.openlocfilehash: 39a3f9299be7dbef4783faa8e6d08fe6ad8461f5
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590309"
---
# <a name="ansi-c-compliance"></a>ANSI C Uyumluluğu

Çalışma zamanı sisteminde (işlevler, makrolar, sabitler, değişkenler ve tür tanımları gibi) Microsoft 'a özgü tüm tanımlayıcıların adlandırma kuralı, ANSI uyumludur. Bu belgede, ANSI/ISO C standartlarını izleyen tüm çalışma zamanı işlevleri, ANSI uyumlu olarak belirtilmiştir. ANSI uyumlu uygulamalar, bu ANSI uyumlu işlevleri yalnızca kullanmalıdır.

Microsoft 'a özgü işlevlerin ve genel değişkenlerin adları tek bir alt çizgi ile başlar. Bu adlar, kodunuzun kapsamı içinde yalnızca yerel olarak geçersiz kılınabilir. Örneğin, Microsoft çalışma zamanı üst bilgi dosyalarını dahil ettiğinizde, `_open` aynı ada sahip yerel bir değişken bildirerek adlı Microsoft 'a özgü işlevi yine de yerel olarak geçersiz kılabilirsiniz. Ancak, bu adı kendi genel işleviniz veya genel değişkeni için kullanamazsınız.

Microsoft 'a özgü makroların ve bildirim sabitlerin adları iki alt çizgi ile veya hemen ardından büyük harfle izlenen tek bir önde gelen alt çizgi ile başlar. Bu tanımlayıcıların kapsamı mutlak. Örneğin, bu nedenle Microsoft 'a özgü tanımlayıcı **_UPPER** kullanamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[Uyumluluk](../c-runtime-library/compatibility.md)
