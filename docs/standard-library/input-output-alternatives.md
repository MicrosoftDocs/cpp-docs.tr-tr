---
title: Giriş-Çıkış Seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28e61dbbd7db6737cd39337acc9925c669cff61d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri

Visual C++ g/ç programlama için birçok seçenek sağlar:

- C çalışma zamanı kitaplığı doğrudan, arabellekten çıkarılan g/ç.

- ANSI C çalışma zamanı kitaplığı akış g/ç.

- Konsol ve bağlantı noktası doğrudan g/ç.

- Microsoft Foundation Class Kitaplığı.

- Microsoft C++ Standart Kitaplığı.

İostream sınıfları için yararlı olan arabelleğe, biçimlendirilmiş metin g/ç. Bir C++ programlama arabirimi gerekir ve Microsoft Foundation Class (MFC) kitaplığı kullanmamaya karar verirseniz, bunlar ayrıca arabellekten çıkarılan veya ikili g/ç için kullanışlıdır. İostream sınıfları bir nesne yönelimli g/ç C çalışma zamanı işlevleri alternatiftir.

Microsoft Windows işletim sistemiyle iostream sınıfları kullanabilirsiniz. Dize hem dosya akışları iş kısıtlamaları, ancak karakter modu akışı nesneleri `cin`, `cout`, `cerr`, ve `clog` Windows grafik kullanıcı arabirimi ile tutarsız. Ayrıca, doğrudan Windows ortamı ile etkileşim özel stream sınıfları türetilemeyeceğini.

## <a name="see-also"></a>Ayrıca bkz.

[Akışın Ne Olduğu](../standard-library/what-a-stream-is.md)<br/>
