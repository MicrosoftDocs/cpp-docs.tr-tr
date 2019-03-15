---
title: .netmodule Giriş Dosyaları Biçimini Seçme
ms.date: 11/04/2016
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
ms.openlocfilehash: d48bfe84210143db333d1e6b081acf1aa66980cf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807338"
---
# <a name="choosing-the-format-of-netmodule-input-files"></a>.netmodule Giriş Dosyaları Biçimini Seçme

Bir MSIL .obj dosyası (ile derlenmiş [/CLR](clr-common-language-runtime-compilation.md)) bir .netmodule dosyası da kullanılabilir.  meta veri ve yerel semboller .obj dosyaları içerir.  netmodule'leri yalnızca meta veriler içerir.

Bir MSIL .obj dosyası için başka bir Visual Studio derleyici / addmodule derleyici seçeneği geçirin (ancak edebilirsiniz .obj dosyası elde edilen derlemenin parçası haline gelir ve bütünleştirilmiş kod ile birlikte gelen unutmayın).  Örneğin, Visual C# ve Visual Basic/addmodule derleyici seçeneği vardır.

> [!NOTE]
>  Çoğu durumda, bağlayıcıya .obj dosyasına .net modülü oluşturulan derlemeden geçmesi gerekir.  Bir .dll veya .netmodule MSIL Modülü dosyasını bağlayıcıya geçirme LNK1107 neden olabilir.

aracılığıyla başvuru ilişkili .h dosyalarla birlikte .obj dosyaları #include, bir .netmodule dosyası yalnızca yönetilen türleri C++ uygulama tarafından tüketilebilecek ise yerel modül türlerini kullanmak C++ uygulamaları izin verin.  Bir .obj dosyasına geçirmeye çalışırsanız #using yerel türleri hakkında bilgi; kullanılamaz # .obj dosyasına ait .h dosyası yerine include.

Diğer Visual Studio derleyicileri, yalnızca yönetilen bir modül türlerinden kullanabilir.

Modülü MSVC bağlayıcı girişi olarak .netmodule veya .obj dosyası kullanmak gerekip gerekmediğini belirlemek için aşağıdakileri kullanın:

- Visual C++ dışında bir Visual Studio derleyici ile oluşturuluyorsa, bir .netmodule üretmek ve bağlayıcı girişi olarak .netmodule kullanın.

- MSVC derleyicisi modüllerin ve modüller kitaplık dışında bir şey oluşturmak için kullanılan, oluşturmak için kullanıyorsanız, bağlayıcı modülü giriş olarak derleyici tarafından üretilmiş .obj dosyalarını kullanın. .netmodule dosyası, giriş olarak kullanmayın.

- Modüllerinizi (bir yönetilmeyen) yerel kitaplık oluşturmak için kullanılan, modülü bağlayıcı girişi olarak .obj dosyaları kullanın ve .lib kitaplık dosyası oluşturur.

- Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı tüm modül giriş (/ CLR: safe ile üretilen) doğrulanabilir olacaksa, modülü bağlayıcı girişi olarak .obj dosyaları kullanın ve bir .dll (derleme) veya .netmodule (Modülü) kitaplık dosyası oluşturur.

- Modüllerinizi yönetilen kitaplık oluşturmak için kullanılan ve bağlayıcı için bir veya daha fazla modül giriş yalnızca/CLR ile üretilecek, modülü bağlayıcı girişi olarak .obj dosyaları kullanın ve bir .dll (derleme) oluşturur.  Kitaplığı'ndan yönetilen türleri ve ayrıca Kitaplığı'nda yerel türler kullanmak için C++ uygulamaları istiyorsanız kullanıma sunmak istiyorsanız, kitaplık (Ayrıca her bir modül için .h dosyaları göndermeye isteyeceksiniz kitaplıkları bileşen modüller için .obj dosyaları oluşur ile başvurulabilir, böylece # kaynak kodundan include).

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Girişi olarak .netmodule Dosyaları](netmodule-files-as-linker-input.md)
