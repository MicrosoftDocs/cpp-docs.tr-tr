---
title: -ENTRY (giriş noktası simgesi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53f5a18b061cbd956731ced6788e86f871ea97bd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719582"
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Giriş Noktası Simgesi)

```
/ENTRY:function
```

## <a name="arguments"></a>Arguments

*İşlevi*<br/>
Bir .exe dosyası veya DLL için kullanıcı tanımlı başlangıç belirten bir işlevi adresi.

## <a name="remarks"></a>Açıklamalar

/ Entry seçeneği, .exe dosyası veya DLL için başlangıç adresi olarak giriş noktası işlevini belirtir.

Kullanılacak işlev tanımlanmalıdır `__stdcall` çağırma kuralı. Parametreler ve dönüş değeri program bir konsol uygulaması, bir windows uygulaması veya bir DLL olup olmadığını bağlıdır. Giriş noktası ayarlayabilir, böylece C çalışma zamanı kitaplığı doğru başlatılmadı ve statik nesneler için C++ oluşturucular yürütülür bağlayıcı izin önerilir.

Varsayılan olarak, başlangıç adresi, C Çalışma Zamanı Kitaplığı'ndan bir işlev adıdır. Bağlayıcı, aşağıdaki tabloda gösterildiği gibi programın özniteliklere göre seçer.

|İşlev adı|İçin varsayılan|
|-------------------|-----------------|
|**mainCRTStartup** (veya **wmainCRTStartup**)|/ Subsystem: Console kullanan bir uygulamayı; çağrıları `main` (veya `wmain`)|
|**WinMainCRTStartup** (veya **wWinMainCRTStartup**)|/ Subsystem kullanan bir uygulamayı:**WINDOWS**; çağrıları `WinMain` (veya `wWinMain`), hangi tanımlanmalıdır kullanmak için `__stdcall`|
|**_DllMainCRTStartup**|BİR DLL; çağrıları `DllMain` varsa, hangi tanımlanmalıdır kullanmak için `__stdcall`|

Varsa [/dll](../../build/reference/dll-build-a-dll.md) veya [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) seçeneği belirtilmezse, bağlayıcı bağlı olarak bir alt sistemi ve giriş noktası seçer `main` veya `WinMain` tanımlanır.

İşlevleri `main`, `WinMain`, ve `DllMain` üç formlar kullanıcı tarafından tanımlanan giriş noktası.

Yönetilen bir görüntü oluşturulurken/Entry için belirtilen işlev imzası olmalıdır (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Kendi ölçümünüzü tanımlayın hakkında bilgi için `DllMain` giriş noktası bkz [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **giriş noktası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)