---
description: Hakkında daha fazla bilgi edinin:. netmodule giriş dosyaları biçimini seçme
title: .netmodule Giriş Dosyaları Biçimini Seçme
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: ed7e448879e983ace7d96cdc7585bf0303378114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179214"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule Giriş Dosyaları Biçimini Seçme

Bir MSIL. obj dosyası ( [/clr](clr-common-language-runtime-compilation.md)ile derlenen),. netmodule dosyası olarak da kullanılabilir.  . obj dosyaları meta verileri ve yerel sembolleri içerir.  . netmodules yalnızca meta veriler içerir.

Bir MSIL. obj dosyasını/addmodule derleyici seçeneği aracılığıyla başka bir Visual Studio derleyicisine geçirebilirsiniz (ancak,. obj dosyasının elde edilen derlemenin bir parçası haline geldiğini ve derlemeyle birlikte gönderilmesinin gerektiğini unutmayın).  Örneğin, Visual C# ve Visual Basic/addmodule derleyici seçeneğine sahiptir.

> [!NOTE]
> Çoğu durumda, .net modülünü oluşturan derlemeden. obj dosyasını bağlayıcıya geçirmeniz gerekir.  Bir. dll veya. netmodule MSIL modül dosyasının bağlayıcıya geçirilmesi LNK1107 ile sonuçlanabilir.

. obj dosyaları ile birlikte, kaynak içinde #include ile başvuru yaptığınız ilişkili. h dosyalarıyla birlikte, C++ uygulamalarının modüldeki yerel türleri kullanmasına izin verir, ancak bir. netmodule dosyasında, yalnızca yönetilen türler bir C++ uygulaması tarafından tüketilebilir.  Bir. obj dosyasını #using geçirmeye çalışırsanız yerel türler hakkında bilgi kullanılamaz; Bunun yerine. obj dosyasının. h dosyasını #include.

Diğer Visual Studio derleyicileri, yalnızca bir modülden yönetilen türleri tüketebilir.

MSVC bağlayıcısına modül girişi olarak bir. netmodule veya. obj dosyası kullanmanıza gerek olup olmadığını anlamak için aşağıdakileri kullanın:

- Visual C++ dışında bir Visual Studio derleyicisi oluşturuyorsanız, bir. netmodule oluşturun ve bağlayıcıya giriş olarak. netmodule kullanın.

- Modül üretmek için MSVC derleyicisini kullanıyorsanız ve modüller bir kitaplık dışında bir şey oluşturmak için kullanılacaksa, derleyici tarafından bağlayıcıya modül girişi olarak üretilen. obj dosyalarını kullanın; . netmodule dosyasını girdi olarak kullanmayın.

- Modülleriniz yerel (yönetilmeyen) bir kitaplık oluşturmak için kullanılacaksa,. obj dosyalarını bağlayıcıya modül girişi olarak kullanın ve bir. lib kitaplık dosyası oluşturun.

- Modülleriniz yönetilen bir kitaplık oluşturmak için kullanılacaksa ve bağlayıcıya tüm modül girdisi doğrulanabilir (/clr: Safe ile üretildi),. obj dosyalarını bağlayıcıya modül girişi olarak kullanın ve bir. dll (Assembly) veya. netmodule (modül) kitaplık dosyası oluşturun.

- Modülleriniz yönetilen bir kitaplık oluşturmak için kullanılacaksa ve bağlayıcıya bir veya daha fazla modül girişi yalnızca/CLR ile üretilmiyorsa, bağlayıcıya modül girişi olarak. obj dosyaları kullanın ve bir. dll (derleme) oluşturun.  Kitaplıktan yönetilen türleri göstermek istiyorsanız ve ayrıca C++ uygulamalarının kitaplıkta yerel türleri kullanmasını istiyorsanız, kitaplığınız kitaplıklar bileşen modülleri için. obj dosyalarından oluşur (her modül için. h dosyalarını de göndermek isteyeceksiniz, bu sayede kaynak koddan #include.).

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı girişi olarak. netmodule dosyaları](netmodule-files-as-linker-input.md)
