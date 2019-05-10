---
title: Giriş-Çıkış Seçenekleri
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: 5fb98714a96dedf725ea17332d7c1627e3390896
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221395"
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri

Microsoft C++ derleyici, g/ç programlama için çeşitli alternatifler sağlar:

- C çalışma zamanı kitaplığı doğrudan, arabellekten çıkarılan g/ç.

- ANSI C çalışma zamanı kitaplığı akış g/ç.

- Konsol ve bağlantı noktası g/ç yönlendirir.

- Microsoft Foundation Class Kitaplığı.

- Microsoft C++ Standart Kitaplığı.

İostream sınıfları için yararlıdır, arabelleğe alınmış, biçimlendirilmiş metin g/ç. Ayrıca ikili ya da arabellekten çıkarılan g/ç için kullanışlı bir C++ programlama arabirimi gerekir ve Microsoft Foundation Class (MFC) kitaplığı kullanmamaya karar. C çalışma zamanı işlevleri nesne yönelimli g/ç alternatif iostream sınıflardır.

Microsoft Windows işletim sistemiyle iostream sınıfları kullanabilirsiniz. Dize hem dosya akışları iş kısıtlamaları, ancak karakter modu akışı nesneleri `cin`, `cout`, `cerr`, ve `clog` Windows grafik kullanıcı arabirimi ile tutarsız. Ayrıca, doğrudan Windows ortamı ile etkileşim özel akış sınıfları türetebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Akışın Ne Olduğu](../standard-library/what-a-stream-is.md)<br/>
