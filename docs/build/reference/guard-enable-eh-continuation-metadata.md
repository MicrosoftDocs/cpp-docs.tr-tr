---
title: '/Guard: ehcont (EH devamlılık meta verilerini etkinleştir)'
description: 'Microsoft C++/Guard: ehcont derleyici seçeneğine yönelik başvuru kılavuzu.'
ms.date: 06/03/2020
f1_keywords:
- /guard:ehcont
- VC.Project.VCCLCompilerTool.GuardEHContMetadata
helpviewer_keywords:
- /guard:ehcont
- /guard:ehcont compiler option
ms.openlocfilehash: e8775b331440e932efb16148ee15acf1c740cd6e
ms.sourcegitcommit: 7e011c68ca7547469544fac87001a33a37e1792e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84425540"
---
# <a name="guardehcont-enable-eh-continuation-metadata"></a>/Guard: ehcont (EH devamlılık meta verilerini etkinleştir)

Derleyiciye göre EH devamlılık (EHCONT) meta verilerini oluşturmayı mümkün.

## <a name="syntax"></a>Sözdizimi

> **`/guard:ehcont`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/guard:ehcont`** Seçeneği, derleyicinin bir ikili için tüm geçerli özel durum işleme devamlılık hedeflerinin göreli sanal adreslerinin (RVA) sıralanmış bir listesini oluşturmasına neden olur. Çalışma zamanı `NtContinue` ve `SetThreadContext` yönerge işaretçisi doğrulaması sırasında kullanılır. Varsayılan olarak **`/guard:ehcont`** kapalıdır ve açıkça etkin olmalıdır. Bu seçeneği açıkça devre dışı bırakmak için kullanın **`/guard:ehcont-`** .

Bu **`/guard:ehcont`** seçenek, Visual Studio 2019 sürüm 16,7 ve sonraki sürümlerinde kullanılabilir. Özelliği, 64 bit IŞLETIM sisteminde 64 bitlik süreçler için desteklenir.

[Denetim akışı zorlama teknolojisi (CET)](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf) , return-odaklı programlama (ROP) tabanlı saldırılara karşı koruyan donanım tabanlı bir güvenlik özelliğidir. Denetim akışı bütünlüğünü zorlamak için her çağrı yığını için bir "gölge yığını" sağlar.

Gölge yığınları, ROP saldırılarını engellemek için kullanılabilir olduğunda, saldırganlar diğer yararlanma tekniklerini kullanmak üzere taşınır. Kullanmanın bir tekniği, [bağlam](/windows/win32/api/winnt/ns-winnt-context) yapısının içindeki yönerge işaretçisi değerini bozmasıdır. Bu yapı,, ve gibi bir iş parçacığının yürütmesini yeniden yönlendiren Sistem çağrılarına geçirilir `NtContinue` [`RtlRestoreContext`](/windows/win32/api/winnt/nf-winnt-rtlrestorecontext) [`SetThreadContext`](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadcontext) . `CONTEXT`Yapı bellekte depolanır. İçerdiği yönerge işaretçisini bozan, sistem çağrılarının bir saldırgan denetimli adrese aktarılmasına neden olabilir. Şu anda `NTContinue` herhangi bir devamlılık noktasıyla çağrılabilir. Bu nedenle, gölge yığınları etkinleştirildiğinde yönerge işaretçisini doğrulamak önemlidir.

`RtlRestoreContext`ve `NtContinue` , yapılandırılmış özel durum işleme (SEH) özel durumu bloğunu içeren hedef çerçeveye geriye doğru geri sarma sırasında kullanılır `__except` . `__except`Blok işaretçisi doğrulamasında başarısız olacağından, bloğun yönerge işaretçisinin gölge yığında olması beklenmez. **`/guard:ehcont`** Derleyici anahtarı bir "Eh devamlılık tablosu" oluşturur. İkili içindeki tüm geçerli özel durum işleme devam hedeflerinin RVA bir sıralanmış listesini içerir. `NtContinue`önce Kullanıcı tarafından sağlanan yönerge işaretçisinin gölge yığınını denetler ve yönerge işaretçisi orada bulunmazsa, yönerge işaretçisini içeren ikiliden EH devamlılık tablosunu denetlemeye devam eder. Kapsayan ikili tablo ile derlenmediyse, eski ikili dosyalarla uyumluluk için `NtContinue` devam etmesine izin verilir. Bir EHCONT verisi olmayan eski ikililer arasında ayrım yapmak önemlidir ve EHCONT verileri içeren ikili dosyalar ancak tablo girişi yoktur. Eski, ikilinin içindeki tüm adreslere geçerli devamlılık hedefleri olarak izin verir. İkinci değer, geçerli bir devamlılık hedefi olarak ikili içindeki hiçbir adrese izin vermez.

**`/guard:ehcont`** Bir ikili IÇIN Eh devamlılık hedefi RVA oluşturmak üzere hem derleyiciye hem de bağlayıcıya geçirilmesi gerekir. İkili 'niz tek bir komut kullanılarak derlenirse `cl` , derleyici seçeneği bağlayıcıya geçirir. Derleyici Ayrıca [**`/guard:cf`**](guard-enable-control-flow-guard.md) seçeneğini bağlayıcıya geçirir. Ayrı olarak derleyip bağlarsanız, bu seçeneklerin hem derleyici hem de bağlayıcı komutlarında ayarlanması gerekir.

Kullanılarak derlenen kodu, **`/guard:ehcont`** Kitaplıklar ve derleme olmadan derlenen nesne dosyaları için bağlayabilirsiniz. Bağlayıcı aşağıdaki senaryolardan birinde önemli bir hata döndürür:

- Kod bölümünde "yerel geriye doğru izleme" bulunur. Daha fazla bilgi için bkz. [try-finally deyimindeki](../../cpp/try-finally-statement.md#abnormal-termination)olağan dışı sonlandırma.

- Bir EH (XData) bölümü bir kod bölümünün işaretçilerini içerir ve bu, SEH için değildir.

- İşaretçiler SEH içindir, ancak nesne dosyası işlev düzeyi bağlama ([/GY](gy-enable-function-level-linking.md)) kullanılarak, Comtts oluşturmak için derlenmedi.

Bağlayıcı önemli bir hata döndürür, çünkü bu senaryolarda meta veriler üretemiyor. Bunun anlamı, bir özel durumun oluşturulmasından dolayı çalışma zamanında kilitlenmeye neden olabilir.

Comamats 'de bulunan ancak kullanılarak derlenmediği SEH bölüm bilgileri için **`/guard:ehcont`** bağlayıcı, uyarı **LNK4291**yayar. Bu durumda bağlayıcı, bölüm için doğru ancak klasik meta veriler üretir. Bu uyarıyı yoksaymak için [/Ignore (belirli uyarıları yoksay)](ignore-ignore-specific-warnings.md)seçeneğini kullanın.

Bağlayıcı meta veriler üretemiyor, aşağıdaki hatalardan birini yayar:

- **`LNK2046`**`: module contains _local_unwind but was not compiled with /guard:ehcont`

- **`LNK2047`**`: module contains C++ EH or complex EH metadata but was not compiled with /guard:ehcont.`

Bir ikilinin EHCONT verisi içerip içerbir şekilde olup olmadığını denetlemek için, ikilinin Yük config dosyasına göz atmak için aşağıdaki öğeleri inceleyin:

```cmd
e:\>link /dump /loadconfig CETTest.exe
...
            10417500 Guard Flags
...
                       EH Continuation table present      // EHCONT guard flag present
...
    0000000180018640 Guard EH continuation table
                  37 Guard EH continuation count          // May be 0 if no exception handling is used in the binary. Still counts has having EHCONT data.
...
    Guard EH Continuation Table                           // List of RVAs

          Address
          --------
           0000000180002CF5
           0000000180002F03
           0000000180002F0A
...
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod oluşturma** özellik sayfasını seçin.

1. **Eh devamlılık meta verilerini etkinleştir** özelliğini seçin.

1. Açılan denetimde, EH devam eden meta verileri etkinleştirmek için **Evet (/Guard: ehcont)** seçeneğini belirleyin veya devre dışı bırakmak için **Hayır (/Guard: ehcont-)** öğesini seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Guard (denetim akışı korumasını etkinleştir)](guard-enable-control-flow-guard.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
