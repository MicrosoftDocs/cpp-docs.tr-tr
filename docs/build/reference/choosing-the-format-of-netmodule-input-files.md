---
title: .netmodule Giriş Dosyaları Biçimini Seçme
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: b4d4b80e4b9195d184b9d97cea67bbaaa3d7d843
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320569"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule Giriş Dosyaları Biçimini Seçme

Bir MSIL .obj dosyası [(/clr](clr-common-language-runtime-compilation.md)ile derlenmiş) .netmodule dosyası olarak da kullanılabilir.  .obj dosyaları meta veriler ve yerel semboller içerir.  .netmodules yalnızca meta veri içerir.

Bir MSIL .obj dosyasını /addmodule derleyici sevesi seçeneği ile başka bir Visual Studio derleyicisine iletebilirsiniz (ancak .obj dosyasının ortaya çıkan derlemenin bir parçası olduğunu ve montajla birlikte gönderilmesi gerektiğini unutmayın).  Örneğin, Visual C# ve Visual Basic /addmodule derleyici seçeneğine sahiptir.

> [!NOTE]
> Çoğu durumda, .net modüloluşturulan derleme gelen bağlayıcı .obj dosyası geçmek gerekir.  .dll veya .netmodule MSIL modülü dosyasının bağlayıcıya geçirilmesi LNK1107 ile sonuçlanabilir.

.obj dosyaları, kaynakolarak #include yoluyla başvuruda bulunan ilişkili .h dosyalarıyla birlikte, C++ uygulamalarının modüldeki yerel türleri tüketmesine izin verir, ancak bir .netmodule dosyasında yalnızca yönetilen türler C++ uygulaması tarafından tüketilebilir.  Bir .obj dosyasını #using'a geçirmeye çalışırsanız, yerel türler hakkında bilgi kullanılamaz; bunun yerine .obj dosyasının .h dosyasını #include.

Diğer Visual Studio derleyicileri yalnızca bir modülden yönetilen türleri tüketebilir.

MSVC bağlayıcısına modül girişi olarak .netmodule veya .obj dosyası kullanmanız gerekip gerekmediğini belirlemek için aşağıdakileri kullanın:

- Visual C++dışında bir Visual Studio derleyicisi ile oluşturuyorsanız, bir .netmodule üretin ve .netmodule'ı bağlayıcıya giriş olarak kullanın.

- Modül üretmek için MSVC derleyicisini kullanıyorsanız ve modül(ler) kitaplık dışında bir şey oluşturmak için kullanılacaksa, bağlayıcıya modül girişi olarak derleyici tarafından üretilen .obj dosyalarını kullanın; .netmodule dosyasını giriş olarak kullanmayın.

- Modülleriniz yerel (yönetilen değil) kitaplık oluşturmak için kullanılacaksa, .obj dosyalarını bağlayıcıya modül girişi olarak kullanın ve bir .lib kitaplık dosyası oluşturun.

- Modülleriniz yönetilen bir kitaplık oluşturmak için kullanılacaksa ve bağlayıcıya tüm modül girişi doğrulanabilir (/clr:safe ile üretilecekse), bağlantıcıya modül girişi olarak .obj dosyalarını kullanın ve bir .dll (derleme) veya .netmodule (modül) kitaplık dosyası oluşturun.

- Modülleriniz yönetilen bir kitaplık oluşturmak için kullanılacaksa ve bağlayıcıya bir veya daha fazla modül girişi yalnızca /clr ile üretilecekse, bağlantıcıya modül girişi olarak .obj dosyalarını kullanın ve bir .dll (derleme) oluşturun.  Kitaplıktan yönetilen türleri ortaya çıkarmak istiyorsanız ve C++ uygulamalarının kitaplıktaki yerel türleri de tüketmesini istiyorsanız, kitaplığınız kitaplıkbileşeni modülleri için .obj dosyalarından oluşur (ayrıca her modül için .h dosyalarını göndermeniz gerekir, böylece kaynak kodundan #include ile başvurulabilirler).

## <a name="see-also"></a>Ayrıca bkz.

[.netmodule Dosyalar Linker Girişi olarak](netmodule-files-as-linker-input.md)
