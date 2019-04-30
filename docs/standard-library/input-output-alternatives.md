---
title: Giriş-Çıkış Seçenekleri
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: bc595b64c991ada8e958e71e13f8cb9d134adb8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404968"
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri

Visual C++, g/ç programlama için çeşitli seçenekler sunar:

- C çalışma zamanı kitaplığı doğrudan, arabellekten çıkarılan g/ç.

- ANSI C çalışma zamanı kitaplığı akış g/ç.

- Konsol ve bağlantı noktası g/ç yönlendirir.

- Microsoft Foundation Class Kitaplığı.

- Microsoft C++ Standart Kitaplığı.

İostream sınıfları için yararlıdır, arabelleğe alınmış, biçimlendirilmiş metin g/ç. Ayrıca ikili ya da arabellekten çıkarılan g/ç için kullanışlı bir C++ programlama arabirimi gerekir ve Microsoft Foundation Class (MFC) kitaplığı kullanmamaya karar. C çalışma zamanı işlevleri nesne yönelimli g/ç alternatif iostream sınıflardır.

Microsoft Windows işletim sistemiyle iostream sınıfları kullanabilirsiniz. Dize hem dosya akışları iş kısıtlamaları, ancak karakter modu akışı nesneleri `cin`, `cout`, `cerr`, ve `clog` Windows grafik kullanıcı arabirimi ile tutarsız. Ayrıca, doğrudan Windows ortamı ile etkileşim özel akış sınıfları türetebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Akışın Ne Olduğu](../standard-library/what-a-stream-is.md)<br/>
