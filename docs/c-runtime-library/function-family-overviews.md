---
title: İşlev ailesine genel bakış
description: Aile ile Microsoft C çalışma zamanı işlevlerine genel bakış.
ms.date: 10/05/2020
ms.assetid: b05a2755-9d11-4ea9-ab97-d00a4e872e16
ms.openlocfilehash: de5192cd03c3821afc646241d75a3e8c6c8c12e3
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806519"
---
# <a name="function-family-overview"></a>İşlev ailesine genel bakış

Bu bölümde, işlev ailesine göre C çalışma zamanı kitaplığı yordamları listelenir.

## <a name="crt-library-routine-families"></a>CRT kitaplık rutin aileleri

[_exec, _wexec](exec-wexec-functions.md)\
Yeni bir işlem yüklemek ve yürütmek için işlevler.

[Dosya adı arama işlevleri](filename-search-functions.md)\
Belirtilen dosya adlarını aramak ve aramaları kapatmak için işlevler.

[Ve için biçim belirtimi sözdizimi `printf``wprintf`](format-specification-syntax-printf-and-wprintf-functions.md)\
Ve için biçim dizesini ve bağımsız değişkenlerini `printf` açıklar `wprintf` .

[Biçim belirtimi alan karakterleri: `scanf` ve `wscanf`](format-specification-fields-scanf-and-wscanf-functions.md)\
Tüm işlev ailesi için bir giriş akışını ayrıştırmak üzere biçim belirtimi alanlarını açıklar `scanf` .

[`is`, `isw` işlevler](is-isw-routines.md)\
Karakterlerin büyük, ASCII, sayısal, noktalama vb. gibi şeyler için test edilmesine yönelik işlevler.

[`_ismbb` lerdir](ismbb-routines.md)\
Bir tamsayı değerini bir Alfa karakterini, boş karakteri, bir yazdırma karakterini temsil edip etmeksizin test etmek için işlevler.

[`_ismbc` lerdir](ismbc-routines.md)\
Bir çok baytlı karakteri bir Alfa karakterini, boş karakteri, bir yazdırma karakterini temsil edip etmeksizin test etmek için işlevler.

[işleç `delete` (CRT)](delete-operator-crt.md)\
Visual Studio 2013 başlayarak, evrensel C çalışma zamanı (UCRT) artık C++ özel işleci Delete işlevini desteklememektedir. Artık C++ standart kitaplığı 'nın bir parçasıdır.

[işleç `new` (CRT)](new-operator-crt.md)\
Visual Studio 2013 başlayarak, evrensel C çalışma zamanı (UCRT) artık C++ özel operator new işlevini desteklememektedir. Artık C++ standart kitaplığı 'nın bir parçasıdır.

[`printf` Konumsal parametre işlevleri](printf-p-positional-parameters.md)\
Konumsal parametreler, bağımsız değişkenlerin bir biçim dizesindeki bir alana yerine geçen sayıya göre belirtir.

[`scanf` tür alanı karakterleri](scanf-type-field-characters.md)\
Tür karakteri, ilişkili bağımsız değişkenin, gibi `scanf` Güvenli sürümler dahil olmak üzere herhangi bir işlev ailesinden bir karakter, dize veya sayı olarak yorumlanıp yorumlanmadığını belirler `scanf_s` .

[`scanf` genişlik belirtimi](scanf-width-specification.md)\
Width alanı, bu alan için okunacak en fazla karakter sayısını denetleyen pozitif bir ondalık tamsayıdır. , Gibi güvenli sürümler dahil olmak üzere herhangi bir `scanf` işlev ailesinden geçerlidir `scanf_s` .

[_spawn, _wspawn işlevleri](spawn-wspawn-functions.md)\
Yeni bir işlem oluşturmak ve yürütmek için işlevler.

[`strcoll` lerdir](strcoll-functions.md)\
`strcoll`Ve `wcscoll` işlevleri, `LC_COLLATE` yerel ayar kodu sayfasının kategori ayarına göre iki dizeyi karşılaştırır.

[Sayısal değer işlevlerine dize](string-to-numeric-value-functions.md)\
`strtod`İşlev ailesi, null ile sonlandırılmış bir dizeyi sayısal bir değere dönüştürür.

[`vprintf` lerdir](vprintf-functions.md)\
`vprintf`İşlevler bir bağımsız değişken listesi için bir işaretçi alır, biçimlendirir ve sonucu belirtilen hedefe yazar. İşlevler, gerçekleştirilen parametre doğrulamasından farklı olarak, geniş veya tek baytlık karakter dizeleri, çıkış hedefi ve parametrelerin biçim dizesinde kullanılma sırasını belirtmek için destek.

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı kitaplığı başvurusu](c-run-time-library-reference.md)