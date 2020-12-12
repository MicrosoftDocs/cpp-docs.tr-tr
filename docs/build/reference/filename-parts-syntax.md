---
description: 'Hakkında daha fazla bilgi edinin: Filename-Parts sözdizimi'
title: Dosya Adı Parçaları Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 436481d52324b4c638b5fa0a9840ce0d9ef654f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192141"
---
# <a name="filename-parts-syntax"></a>Dosya Adı Parçaları Sözdizimi

Komutdaki dosya adı-parça sözdizimi, ilk bağımlı dosya adının bileşenlerini temsil eder (kapsanan bağımlı olabilir). Dosya adı bileşenleri, diskte olduğu gibi değil, belirtilen dosya sürücü, yol, taban adı ve uzantıdır. Tam dosya adını göstermek için **% s** kullanın. Dosya adının parçalarını göstermek için, her türlü sırada *parçaların* sıfır veya daha fazla olması gibi **% &#124;**[*Parts*]**F** (yüzde simgesini izleyen bir dikey çubuk karakteri) kullanın.

|Letter|Açıklama|
|------------|-----------------|
|Harf yok|Tamamlanma adı ( **% s** ile aynı)|
|**d**|Sürücü|
|**Lama**|Yol|
|**vadeli**|Dosya taban adı|
|**a**|Dosya uzantısı|

Örneğin, dosya adı c:\prog.exe:

- % s c:\prog.exe olacaktır

- % &#124;F c:\prog.exe olacak

- % &#124;dF c olacak

- % &#124;pF c:\ olacak

- % &#124;fF program olacak

- % &#124;eF, exe olacak

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyasındaki komutlar](commands-in-a-makefile.md)
