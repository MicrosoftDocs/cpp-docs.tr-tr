---
title: LIB çıktı dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23665897266bab87c71b8b3889688113fe8aa99a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720713"
---
# <a name="lib-output-files"></a>LIB Çıktı Dosyaları

LIB tarafından oluşturulan çıktı dosyaları, aşağıdaki tabloda gösterildiği gibi çünkü kullanılıyor, modunu bağlıdır.

|Mod|Çıkış|
|----------|------------|
|Varsayılan (oluşturmak veya bir kitaplık değiştirme)|COFF kitaplık (.lib)|
|/ Extract ile bir üyesini ayıklama|Nesne (.obj) dosyası|
|Bir dışarı aktarma dosyası oluşturup ile/def kitaplığı içeri aktarma|Kitaplık (.lib) ve dışarı aktarma (.exp) dosyası içeri aktarma|

## <a name="see-also"></a>Ayrıca Bkz.

[LIB'e Genel Bakış](../../build/reference/overview-of-lib.md)