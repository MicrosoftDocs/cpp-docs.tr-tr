---
title: Parametre Doğrulama
description: Microsoft C çalışma zamanı kitaplığı 'nda parametre doğrulamanın açıklaması.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
ms.openlocfilehash: 60ded7fc5a4388b2c4bf87ab5a388caab5fc47c2
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589828"
---
# <a name="parameter-validation"></a>Parametre Doğrulama

Güvenlik açısından gelişmiş CRT işlevlerinin birçoğu ve çoğu bu değildir, **null**işaretçileri denetlemek, tamsayıların geçerli bir aralıkta olması veya numaralandırma değerlerinin geçerli olması gibi işlemler için parametrelerini doğrulayın. Geçersiz parametre bulunursa, geçersiz parametre işleyicisi çağırılır.

## <a name="invalid-parameter-handler-routine"></a>Geçersiz parametre Işleyicisi yordamı

Bir C çalışma zamanı kitaplığı işlevi geçersiz bir parametre algıladığında, hatayla ilgili bazı bilgileri yakalar ve sonra geçersiz parametre işleyicisi dağıtma işlevini sarmalayan bir makro çağırır. [_İnvalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md)veya [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md)biri olacaktır. Hangi dağıtım işlevi çağrılır, kodunuzun, sırasıyla, hata ayıklama derlemesi, perakende oluşturma veya hata kurtarılabilir olarak kabul edilip edilmeyeceğini bağlıdır.

Hata ayıklama yapılarında, geçersiz parametre makrosu genellikle başarısız bir onaylama işlemi ve dağıtım işlevi çağrılmadan önce bir hata ayıklayıcı kesme noktası oluşturur. Kod yürütüldüğünde onaylama, kullanıcıya "Iptal", "yeniden dene" ve "devam" ya da işletim sistemi ve çalışma zamanı kitaplığı sürümüne göre benzer seçimler içeren bir iletişim kutusunda bildirilebilir. Bu seçenekler, kullanıcının programı hemen sonlanmasına, hata ayıklayıcı eklemeye veya mevcut kodun, dağıtım işlevini çağıran çalışmaya devam etmesine izin verir.

Geçersiz parametre işleyicisi gönderme işlevi şu anda atanmış geçersiz parametre işleyicisini çağırır. Varsayılan olarak, geçersiz parametre çağırır `_invoke_watson` , bu, uygulamanın kapatılmasına ve bir mini döküm oluşturmasına neden olur. İşletim sistemi tarafından etkinleştirildiyse bir iletişim kutusu kullanıcıdan, kilitlenme dökümünü analiz için Microsoft 'a göndermek isteyip istemediği sorulur.

Geçersiz parametre işleyicisini kendi işleviniz olarak ayarlamak için [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) veya [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) işlevlerini kullanarak bu davranışı değiştirebilirsiniz. Belirttiğiniz işlev uygulamayı sonlandıramıyorsa, denetim geçersiz parametreleri alan işleve döndürülür. CRT 'de, bu işlevler normalde işlev yürütmeyi durdurur, `errno` bir hata koduna ayarlanır ve bir hata kodu döndürür. Çoğu durumda, `errno` `EINVAL` geçersiz bir parametreyi belirtmek için değer ve dönüş değeri her ikisi de vardır. Bazı durumlarda, `EBADF` parametre olarak geçirilen hatalı dosya işaretçisi gibi daha belirli bir hata kodu döndürülür. 

Hakkında daha fazla bilgi için `errno` bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="see-also"></a>Ayrıca bkz.

[CRT 'daki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md)\
[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)
