---
description: Daha fazla bilgi edinin:/ENTRY (giriş noktası simgesi)
title: /ENTRY (Giriş Noktası Simgesi)
ms.date: 11/04/2016
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
ms.openlocfilehash: e4966ef44922a3a90d5abb5a7ac23460d4155f92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201020"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Giriş Noktası Simgesi)

```
/ENTRY:function
```

## <a name="arguments"></a>Arguments

*çalışmayacaktır*<br/>
Bir. exe dosyası veya DLL için Kullanıcı tanımlı başlangıç adresini belirten bir işlev.

## <a name="remarks"></a>Açıklamalar

/ENTRY seçeneği bir. exe dosyası veya DLL için başlangıç adresi olarak bir giriş noktası işlevi belirtir.

Çağırma kuralını kullanmak için işlevin tanımlanması gerekir **`__stdcall`** . Program bir konsol uygulaması, bir Windows uygulaması veya DLL ise, parametreler ve dönüş değeri öğesine bağlıdır. Bağlayıcının giriş noktasını, C çalışma zamanı kitaplığının doğru şekilde başlatılması ve statik nesneler için C++ oluşturucuları yürütülmesi için ayarlamanız önerilir.

Varsayılan olarak, başlangıç adresi C çalışma zamanı kitaplığından bir işlev adıdır. Bağlayıcı, aşağıdaki tabloda gösterildiği gibi, programın özniteliklerine göre seçer.

|İşlev adı|İçin varsayılan|
|-------------------|-----------------|
|**mainCRTStartup** (veya **wmainCRTStartup**)|/SUBSYSTEM: CONSOLE; kullanan bir uygulama çağrılar `main` (veya `wmain` )|
|**WinMainCRTStartup** (veya **wWinMainCRTStartup**)|/SUBSYSTEM:**WINDOWS**; kullanan bir uygulama `WinMain` `wWinMain` kullanılması için tanımlanması gereken çağrılar (veya) **`__stdcall`**|
|**_DllMainCRTStartup**|BIR DLL; varsa `DllMain` , bunu kullanmak için tanımlanması gereken çağrılar **`__stdcall`**|

[/DLL](dll-build-a-dll.md) veya [/Subsystem](subsystem-specify-subsystem.md) seçeneği belirtilmemişse, bağlayıcı tanımlanmış olup olmadığına bağlı olarak bir alt sistem ve giriş noktası seçer `main` `WinMain` .

, `main` Ve işlevleri `WinMain` `DllMain` Kullanıcı tanımlı giriş noktasının üç formlarıdır.

Yönetilen bir görüntü oluştururken,/ENTRY olarak belirtilen işlevin imzası (LPVOID *var1*, DWORD *var2*, lpvoid *var3*) olmalıdır.

Kendi giriş noktanızı tanımlama hakkında daha fazla bilgi için `DllMain` bkz. [DLL 'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Gelişmiş** Özellik sayfasına tıklayın.

1. **Giriş noktası** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
