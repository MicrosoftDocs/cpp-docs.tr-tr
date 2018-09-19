---
title: Parametre doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 427f585fb7e5c917009ccc013179a364ef2dc619
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030338"
---
# <a name="parameter-validation"></a>Parametre Doğrulama

Gelişmiş Güvenlik CRT işlevlerinin çoğunu ve birçok önceden var olan işlevler kendi parametrelerini doğrular. Bu işaretçiler için denetimi içerebilir **NULL**tamsayılar geçerli bir aralığa düşen denetimi veya numaralandırma değerlerinin geçerli olduğunu kontrol. Geçersiz bir parametre bulunduğunda, geçersiz parametre işleyicisi yürütülür.

## <a name="invalid-parameter-handler-routine"></a>Geçersiz parametre işleyici rutinini

C çalışma zamanı kitaplığı işlevi geçersiz bir parametre algıladığında, bu hata hakkındaki bazı bilgileri yakalar ve ardından bir geçersiz parametre işleyici gönderme işlevi, aşağıdakilerden birini sarmalayan bir makro çağırır [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md), veya [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). Çağrılan gönderme işlev kodunuzu, sırasıyla olup, hata ayıklama derlemesi, perakende derleme üzerinde bağlıdır ve hata kurtarılabilir olarak kabul edilmez.

Dağıtma işlevi çağrılmadan önce hata ayıklama yapılarında, geçersiz parametre makrosu genellikle başarısız bir onaylama işlemi ve hata ayıklayıcı bir kesme noktası oluşturur. Kod yürütüldüğünde, onaylama işlemi "İptal", "Deneyin" ve "Devam" veya işletim sistemi ve çalışma zamanı kitaplığı sürümüne bağlı olarak, benzer seçenekleri içeren bir iletişim kutusu kullanıcı için bildirilebilir. Bu seçenekler, kullanıcı bir hata ayıklayıcı ekleyin ya da çalışmaya devam mevcut kod izin vermek için program hemen sonlandırmak gönderme işlevini çağıran sağlar.

Geçersiz parametre işleyicisi dağıtma işlevinin sırayla şu anda atanmış geçersiz parametre işleyicisini çağırır. Varsayılan olarak, geçersiz parametreyi çağırır `_invoke_watson` neden olan uygulamanın çökmesine"," diğer bir deyişle, sonlandırma ve mini döküm oluşturmak. İşletim sistemi tarafından etkinleştirilirse, bir iletişim kutusu kullanıcı Microsoft'a kilitlenme bilgi dökümü analiz yüklemek isteyip istemediğinizi sorar.

İşlevleri kullanarak bu davranışı değiştirilebilir [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) veya [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) kendi işlevi için geçersiz parametre işleyicisi ayarlamak için. Belirttiğiniz işlevi uygulamayı sonlandırmak değil, geçersiz parametreler alınan işleve döndürülür. CRT bu İşlevler normalde işlevi yürütme sona erecek ayarlamak `errno` bir hata kodu ve bir hata kodu döndürür. Çoğu durumda, `errno` değeri ve dönüş değeri olan hem de `EINVAL`, geçersiz bir parametre belirten. Bazı durumlarda, daha belirgin bir hata kodu, gibi döndürülen `EBADF` bir hatalı dosya işaretçisiyse için geçirilen parametre olarak. Daha fazla bilgi için `errno`, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CRT'deki Güvenlik Özellikleri](../c-runtime-library/security-features-in-the-crt.md)<br/>
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)