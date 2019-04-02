---
title: 'Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe kullanın'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
ms.openlocfilehash: b9016f05b82e3eb04474d370bd069e8008de5278
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787608"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe kullanın

Yerel C++ kodunu ve Windows çalışma zamanı bileşenleri arasındaki etkileşim COM düzeyi Winmdidl.exe ve midlrt.exe etkinleştirin. Giriş meta verileri için bir Windows çalışma zamanı bileşeni içerir ve bir IDL dosyası çıkaran bir .winmd dosyası olarak Winmdidl.exe alır. Midlrt.exe bu IDL dosyası C++ kodu kullanabileceği üstbilgi dosyalarına dönüştürür. Her iki araç komut satırında çalıştırın.

İçinde iki ana senaryo bu araçları kullanabilirsiniz:

- Windows çalışma zamanı Şablon kitaplığı (WRL) kullanılarak yazılan bir C++ uygulamasına özel bir Windows çalışma zamanı bileşeni kullanabilir, böylece özel IDL ve üst bilgi dosyaları oluşturma.

- Kullanıcı tanımlı olay türleri için Ara sunucu ve saplama dosyaları bir Windows çalışma zamanı bileşeni oluşturma. Daha fazla bilgi için [özel olayları ve olay erişimcileri Windows çalışma zamanı bileşenlerinde](/windows/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).

Bu araçlar, yalnızca özel .winmd dosyalarını ayrıştırmak için gereklidir. Windows işletim sistemi bileşenlerinin .idl ve .h dosyaları zaten sizin için oluşturulur. Windows 8.1, varsayılan olarak \Program dosyaları (x86) \Windows Kits\8.1\Include\winrt içinde bulunan\\.

## <a name="location-of-the-tools"></a>Araçlar'ın konumu

Varsayılan olarak [Windows 8.1, winmdidl.exe ve midlrt.exe C:\Program Files (x86) \Windows Kits\8.1 içinde bulunduğu\\. Araçların sürümleri \bin\x86\ ve \bin\x64\ klasörler de mevcuttur.

## <a name="winmdidl-command-line-arguments"></a>Winmdidl komut satırı bağımsız değişkenleri

```
Winmdidl.exe [/nologo] [/suppressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile
```

**/nologo**<br/>
Konsol winmdidl telif hakkı iletisi ve sürüm numarasını görüntülenmesini önler.

**/suppressversioncheck**<br/>
Kullanılmadı.

**/ saat**<br/>
Toplam yürütme süresi, konsol çıkışında görüntüler.

**/OutDir:**<em>dizini</em><br/>
Çıktı dizini belirtir. Yol boşluklar içeriyorsa, tırnak işaretleri kullanın. Varsayılan çıkış dizini  *\<sürücüsü >*: \Users\\*\<kullanıcıadı >* \AppData\Local\VirtualStore\Program dosyaları (x86) \Microsoft Visual Studio 12.0\\.

**/ Başlık:**<em>dosyası</em><br/>
Varsayılan telif hakkı iletisini ve oluşturulan .idl dosyasının en üstüne winmdidl sürüm numarasına önüne eklediğinizden özel metin içeren bir dosyayı belirtir. Yol boşluklar içeriyorsa, tırnak işaretleri kullanın.

**/UTF8**<br/>
UTF-8 biçimlendirilmesi için dosyayı neden olur.

*Wınmdfıle*<br/>
Ayrıştırılacak .winmd dosyasının adı. Yol boşluklar içeriyorsa, tırnak işaretleri kullanın.

## <a name="midlrt-command-line-arguments"></a>Midlrt komut satırı bağımsız değişkenleri

Bkz: [MIDLRT ve Windows çalışma zamanı bileşenleri](/windows/desktop/Midl/midlrt-and-windows-runtime-components).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, Visual Studio x86 komut isteminde winmdidl komut gösterir. Bu, bir çıktı dizini ve oluşturulan .idl dosyasına eklemek için özel bir başlık metnini içeren bir dosyayı belirtir.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0>winmdidl /nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\Test_for_winmdidl\test_for_winmdidl.winmd"`

Sonraki örnek, işlemin başarılı olduğunu gösteren winmdidl konsol görüntüden gösterir.

**C:\users\giraffe\documents oluşturma\\\Test_for_winmdidl.idl**

Ardından, midlrt oluşturulan IDL dosyası üzerinde çalıştırılır. Dikkat **metadata_dir** .idl dosyasının adını sonra bağımsız değişken belirtildi. \WinMetadata\ yolunu gereklidir; bu Windows.winmd'i konumudur.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0> midlrt "c:\users\mblome\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"`

## <a name="remarks"></a>Açıklamalar

Giriş dosyası ancak .idl dosya adı uzantısına sahip olduğundan winmdidl işlemi çıkış dosyasından aynı ada sahip.

WRL erişilecek bir Windows çalışma zamanı bileşeni geliştiriyorsanız winmdidl.exe ve midlrt.exe .idl ve .h dosyaları her derleme üzerinde oluşturulan derleme sonrası adımları çalıştırılacak belirtebilirsiniz. Bir örnek için bkz. [Raising Events Windows çalışma zamanı bileşenlerinde](/windows/uwp/winrt-components/raising-events-in-windows-runtime-components).