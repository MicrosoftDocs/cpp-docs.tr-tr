---
title: 'Nasıl yapılır: winmdidl.exe ve midlrt.exe windows meta verilerinden .h dosyaları oluşturmak için kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4be8ba11-c223-44ad-9256-7e1edae9a7bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 06fef7449a540fbd3cddc2d38c9ce7483a7b5d55
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891730"
---
# <a name="how-to-use-winmdidlexe-and-midlrtexe-to-create-h-files-from-windows-metadata"></a>Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma
Winmdidl.exe ve midlrt.exe COM düzeyinde etkileşim yerel C++ kod ve Windows çalışma zamanı bileşenleri arasındaki etkinleştirin. Giriş Windows çalışma zamanı bileşeni için meta veriler içeriyor ve bir IDL dosyası çıkaran bir .winmd dosyası olarak Winmdidl.exe alır. Midlrt.exe IDL dosyayı C++ kodu tüketebileceği üstbilgi dosyaları dönüştürür. Her iki Araçları komut satırı üzerinde çalıştırın.  
  
 İki ana senaryolarda bu araçları kullanın:  
  
-   Windows çalışma zamanı Şablon kitaplığı (WRL) kullanılarak yazılmış bir C++ uygulaması özel bir Windows çalışma zamanı bileşeni tüketebileceği böylece özel IDL ve başlık dosyaları oluşturma.  
  
-   Kullanıcı tanımlı olay türleri için proxy ve saplama dosyaları bir Windows çalışma zamanı bileşeni oluşturma. Daha fazla bilgi için bkz: [özel olayları ve Windows çalışma zamanı bileşenleri olay erişimcileri](/uwp/winrt-components/custom-events-and-event-accessors-in-windows-runtime-components).  
  
 Bu araçlar, yalnızca özel .winmd dosyalarını ayrıştırmak için gereklidir. Windows işletim sistemi bileşenlerinin .idl ve .h dosyaları zaten sizin için oluşturulur. Varsayılan olarak [!INCLUDE[win81](../misc/includes/win81_md.md)], \Program dosyaları (x86) \Windows Kits\8.1\Include\winrt bulundukları\\.  
  
## <a name="location-of-the-tools"></a>Araçlar konumu  
 Varsayılan olarak [!INCLUDE[win81](../misc/includes/win81_md.md)], winmdidl.exe ve midlrt.exe C:\Program Files (x86) \Windows Kits\8.1 bulunur\\. Araçların sürümleri \bin\x86\ ve \bin\x64\ klasörlerinde de kullanılabilir.  
  
## <a name="winmdidl-command-line-arguments"></a>Winmdidl komut satırı bağımsız değişkenleri  
  
```  
Winmdidl.exe [/nologo] [/supressversioncheck] [/time] [/outdir:dir] [/banner:file] [/utf8] Winmdfile  
```  
  
 `/nologo`  
 Sürüm numarasını ve telif hakkı iletisi winmdidl konsol görüntülenmesini engeller.  
  
 `/supressversioncheck`  
 Kullanılmadı.  
  
 `/time`  
 Toplam yürütme süresi konsol çıktısı görüntüler.  
  
 OutDir:\<dir >  
 Bir çıkış dizini belirtir. Yol boşluk içeriyorsa, tırnak işaretleri kullanın. Varsayılan çıkış dizini  *\<sürücü >*: \Users\\*\<kullanıcı adı >* \AppData\Local\VirtualStore\Program dosyaları (x86) \Microsoft Visual Studio 12.0\\.  
  
 `/banner:<file>`  
 Varsayılan telif hakkı iletisi ve dosyanın üst kısmındaki oluşturulan .idl winmdidl sürüm numarası önüne eklediğinizden özel metin içeren bir dosyayı belirtir. Yol boşluk içeriyorsa, tırnak işaretleri kullanın.  
  
 `/utf8`  
 Dosyanın UTF-8 olarak biçimlendirilmiş olması neden olur.  
  
 `Winmdfile`  
 Ayrıştırılacak .winmd dosyasının adı. Yol boşluk içeriyorsa, tırnak işaretleri kullanın.  
  
## <a name="midlrt-command-line-arguments"></a>Midlrt komut satırı bağımsız değişkenleri  
 Bkz: [MIDLRT ve Windows çalışma zamanı bileşenleri](http://msdn.microsoft.com/library/windows/desktop/hh869900\(v=vs.85\).aspx).  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, Visual Studio x86 komut isteminde winmdidl komut gösterir. Bir çıkış dizini ve oluşturulan .idl dosyasına eklemek için özel başlık metni içeren bir dosyayı belirtir.  
  
 **C:\Program Files (x86) \Microsoft Visual Studio 12.0 > winmdidl/nologo /outdir:c:\users\giraffe\documents\ /banner:c:\users\giraffe\documents\banner.txt "C:\Users\giraffe\Documents\Visual Studio 2013\Projects\Test_for_winmdidl\Debug\ Test_for_winmdidl\test_for_winmdidl.winmd"**  
  
 Sonraki örnek işlemin başarılı olduğunu gösteren winmdidl konsol görüntüden gösterir.  
  
 **C:\users\giraffe\documents oluşturma\\\Test_for_winmdidl.idl**  
  
 Ardından, midlrt oluşturulan IDL dosyada çalıştırılır. Dikkat **metadata_dir** bağımsız değişkeni .idl dosya adından sonra belirtilir. \WinMetadata\ yol gereklidir — windows.winmd için konumdur.  
  
 **C:\Program Files (x86) \Microsoft Visual Studio 12.0 > midlrt "c:\users\mblome\documents\test_for_winmdidl.idl" /metadata_dir "C:\Windows\System32\WinMetadata"**  
  
## <a name="remarks"></a>Açıklamalar  
 Giriş dosyası ancak .idl dosya adı uzantısına sahip olarak winmdidl işlemi çıktı dosyasından aynı ada sahip.  
  
 WRL erişilen bir Windows çalışma zamanı bileşeni geliştiriyorsanız winmdidl.exe ve midlrt.exe her yapı üzerinde oluşturulan .idl ve .h dosyaları oluşturma sonrası adımları çalıştırılacak belirtebilirsiniz. Bir örnek için bkz: [Windows çalışma zamanı bileşenleri oluşturma olaylarda](/uwp/winrt-components/raising-events-in-windows-runtime-components).