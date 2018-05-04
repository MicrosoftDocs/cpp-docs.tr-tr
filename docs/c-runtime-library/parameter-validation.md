---
title: Parametre doğrulaması | Microsoft Docs
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
ms.openlocfilehash: a89ec2cd0b360f498e52af7e49bd5c6571521e2c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="parameter-validation"></a>Parametre Doğrulama
Gelişmiş Güvenlik CRT işlevlerinin çoğunu ve önceden var olan işlevlerin çoğunu kendi parametreleri doğrulayın. Bu NULL işaretçiler denetimi, tamsayılar geçerli bir aralık kalan denetleme veya numaralandırma değerlerinin geçerli olduğundan emin denetimi içerebilir. Geçersiz bir parametre bulunduğunda, geçersiz parametre işleyicisi yürütülür.  
  
## <a name="invalid-parameter-handler-routine"></a>Geçersiz parametre işleyicisi yordamı  
 C çalışma zamanı kitaplığı işlevi geçersiz bir parametre algıladığında, bu hata hakkındaki bazı bilgileri yakalar ve ardından bir geçersiz parametre işleyicisi gönderme işlevi, aşağıdakilerden birini sarmalar makrosu çağırır [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md), veya [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). Adlı gönderme işlevi bağlıdır kodunuzu, sırasıyla olup, bir hata ayıklama derlemesi, perakende derleme üzerinde veya hata kurtarılabilir dikkate alınmaz. 
 
 Gönderme işlevi çağrılmadan önce hata ayıklama derlemelerinde, geçersiz bir parametre makrosu genellikle başarısız onaylama ve bir hata ayıklayıcı kesme noktası başlatır. Kodu yürütüldüğünde, onaylama işlemi kullanıcı, "İptal", "Yeniden deneme," ve "Devam et" veya benzer seçenekler, işletim sistemi ve çalışma zamanı kitaplığı sürümüne bağlı olarak bulunan bir iletişim kutusu için bildirilebilir. Bu seçenekler gönderme işlevini çağırır hemen bir hata ayıklayıcısı eklemeniz veya çalışmaya devam var olan kodu izin vermek için program sonlandırma kullanıcıya izin verir. 
 
 Geçersiz parametre işleyicisi gönderme işlevi sırayla şu anda atanmış geçersiz parametre işleyicisi çağırır. Varsayılan olarak, geçersiz bir parametre çağırır `_invoke_watson` neden olan uygulama çökmesine"," başka bir deyişle, sonlandırma ve bir mini döküm oluşturmak. İşletim sistemi tarafından etkinleştirilirse, bir iletişim kutusu, kullanıcı bunlar Microsoft kilitlenme dökümü çözümleme için yük isteyip istemediğinizi sorar.   
  
 Bu davranış işlevlerini kullanarak değiştirilebilir [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) veya [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) kendi işlevi için geçersiz parametre işleyicisi ayarlamak için. Belirttiğiniz işlevi uygulamayı sonlandırmak değil, geçersiz parametreleri aldı işlevi döndürülür. CRT bu İşlevler normalde işlevi yürütme durduracak ayarlamak `errno` bir hata kodu ve return bir hata kodu. Çoğu durumda, `errno` ve dönüş değerleri olan her ikisi de `EINVAL`, geçersiz bir parametre belirten. Bazı durumlarda, bir daha özel döndürülen hata kodu, gibi `EBADF` hatalı dosya işaretçi geçirilen parametre olarak. Daha fazla bilgi için `errno`, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)