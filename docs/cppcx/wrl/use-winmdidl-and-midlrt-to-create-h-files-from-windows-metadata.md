---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: Windows meta verilerinden. h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe kullanma'
title: 'Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
ms.openlocfilehash: be76f0cb898017c575356f90fcd043f987a0dbad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209262"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma

Winmdidl.exe ve midlrt.exe yerel C++ kodu ve Windows Çalışma Zamanı bileşenleri arasında COM düzeyi etkileşimini etkinleştirir. Winmdidl.exe, bir Windows Çalışma Zamanı bileşeni için meta veriler içeren bir. winmd dosyası alır ve bir IDL dosyası verir. Midlrt.exe, bu IDL dosyasını C++ kodunun tüketebileceği üstbilgi dosyalarına dönüştürür. Her iki araç de komut satırında çalışır.

Bu araçları iki ana senaryoda kullanabilirsiniz:

- Windows Çalışma Zamanı şablon kitaplığı (WRL) kullanılarak yazılmış bir C++ uygulamasının özel bir Windows Çalışma Zamanı bileşeni kullanabilmesi için özel IDL ve üstbilgi dosyaları oluşturma.

- Windows Çalışma Zamanı bileşenindeki Kullanıcı tanımlı olay türleri için proxy ve saplama dosyaları oluşturuluyor. Daha fazla bilgi için [Windows Çalışma Zamanı bileşenlerinde özel olaylar ve olay erişimcileri](/windows/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components)' ne bakın.

Bu araçlar yalnızca Custom. winmd dosyalarını ayrıştırmak için gereklidir. Windows işletim sistemi bileşenleri için. IDL ve. h dosyaları zaten sizin için oluşturulmuştur. Varsayılan olarak Windows 8.1, \Program Files (x86) \Windows Kits\8.1\ınclude\wınrt dizininde bulunur \\ .

## <a name="location-of-the-tools"></a>Araçların konumu

Varsayılan olarak, [Windows 8.1, winmdidl.exe ve midlrt.exe C:\Program Files (x86) \Windows Kits\8.1 ' de bulunur \\ . Araçların sürümleri, \bin\x86\ ve \bin\x64\ klasörlerinde de mevcuttur.

## <a name="winmdidl-command-line-arguments"></a>Winmdıdl komut satırı bağımsız değişkenleri

```
Winmdidl.exe [/nologo] [/suppressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile
```

**/nologo**<br/>
Winmdıdl telif hakkı iletisi ve sürüm numarasının konsol görüntüsünü önler.

**/suppressversioncheck**<br/>
Kullanılmadı.

**/Saat**<br/>
Konsol çıkışında toplam yürütme süresini görüntüler.

**/OutDir:**<em>dir</em><br/>
Bir çıkış dizini belirtir. Yol boşluk içeriyorsa, tırnak işaretleri kullanın. Varsayılan çıkış dizini *\<drive>* : \Users \\ *\<username>* \Appdata\local\virtualstore\program Files (x86) \microsoft Visual Studio 12,0 \\ .

**/Banner:**<em>Dosya</em><br/>
Oluşturulan. IDL dosyasının en üstünde varsayılan telif hakkı iletisine ve winmdıdl sürüm numarasına eklenecek özel metin içeren bir dosyayı belirtir. Yol boşluk içeriyorsa, tırnak işaretleri kullanın.

**/UTF8**<br/>
Dosyanın UTF-8 olarak biçimlendirilmesini sağlar.

*WINMDFILE*<br/>
Ayrıştırılacak. winmd dosyasının adı. Yol boşluk içeriyorsa, tırnak işaretleri kullanın.

## <a name="midlrt-command-line-arguments"></a>MIDLRT komut satırı bağımsız değişkenleri

Bkz. [MIDLRT ve Windows çalışma zamanı bileşenleri](/windows/win32/Midl/midlrt-and-windows-runtime-components).

## <a name="examples"></a>Örnekler

Aşağıdaki örnekte, bir Visual Studio x86 komut isteminde bir winmdıdl komutu gösterilmektedir. Bir çıktı dizini ve oluşturulan. IDL dosyasına eklemek için özel başlık metni içeren bir dosya belirtir.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0>winmdidl /nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\Test_for_winmdidl\test_for_winmdidl.winmd"`

Sonraki örnekte, işlemin başarılı olduğunu belirten winmdıdl 'den görüntülenen konsol gösterilmektedir.

**C:\users\giraffe\documents \\ \ Test_for_winmdidl. IDL oluşturuluyor**

Ardından, MIDLRT oluşturulan IDL dosyasında çalıştırılır. **Metadata_dir** bağımsız değişkeninin. IDL dosyasının adından sonra belirtildiğine dikkat edin. \WinMetadata\ ' nin yolu gereklidir; Windows. winmd 'nin konumudur.

`C:\Program Files (x86)\Microsoft Visual Studio 12.0> midlrt "c:\users\username\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"`

## <a name="remarks"></a>Açıklamalar

Bir winmdıdl işlemindeki çıkış dosyası, giriş dosyasıyla aynı ada sahip ancak. IDL dosya adı uzantısına sahip.

WRL 'den erişilecek bir Windows Çalışma Zamanı bileşeni geliştiriyorsanız, her derlemede. IDL ve. h dosyalarının oluşturulması için derleme sonrası adımlar olarak çalışacak winmdidl.exe ve midlrt.exe ' i belirtebilirsiniz. Bir örnek için bkz. [Windows Çalışma Zamanı bileşenlerinde olayları yükseltme](/windows/uwp/winrt-components/raising-events-in-windows-runtime-components).
