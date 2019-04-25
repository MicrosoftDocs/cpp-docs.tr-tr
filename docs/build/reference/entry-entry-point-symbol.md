---
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
ms.openlocfilehash: 0f3604ef75ce10928463c088e423615886555eda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293218"
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

Varsa [/dll](dll-build-a-dll.md) veya [/Subsystem](subsystem-specify-subsystem.md) seçeneği belirtilmezse, bağlayıcı bağlı olarak bir alt sistemi ve giriş noktası seçer `main` veya `WinMain` tanımlanır.

İşlevleri `main`, `WinMain`, ve `DllMain` üç formlar kullanıcı tarafından tanımlanan giriş noktası.

Yönetilen bir görüntü oluşturulurken/Entry için belirtilen işlev imzası olmalıdır (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).

Kendi ölçümünüzü tanımlayın hakkında bilgi için `DllMain` giriş noktası bkz [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../run-time-library-behavior.md) .

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **giriş noktası** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
