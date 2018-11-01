---
title: x64 (ml64.exe) için (MASM)
ms.date: 08/30/2018
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 0404bff54a08988a72fcb0a0c075a4446bf90f48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596228"
---
# <a name="masm-for-x64-ml64exe"></a>x64 (ml64.exe) için (MASM)

Visual Studio hem 32-bit hem de 64-bit barındırılan sürümlerine Microsoft Assembler (MASM) hedef x64 kodu içerir. Ml64.exe olarak adlandırılan bu x64 kabul eden assembler, Çevirici dili. MASM komut satırı araçları, Visual Studio yüklemesi sırasında bir C++ iş yükünü seçtiğinizde yüklenir. MASM araçları, ayrı bir indirme olarak kullanılamaz. Visual Studio'nun bir kopyasını yükleyip konusunda yönergeler için bkz. [Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio). Tam Visual Studio IDE yüklemek istediğiniz değil ancak yalnızca komut satırı araçlarını istiyorsanız indirme [Visual Studio 2017 için derleme Araçları](https://go.microsoft.com/fwlink/p/?linkid=875721).

Yapı için MASM kullanılacak x64 kodunu komut satırında hedefler, x64 için geliştirici komut istemi kullanın gerekli yolu ve diğer ortam değişkenlerini ayarlar hedefler. Bir geliştirici komut istemi başlatmak üzere hakkında daha fazla bilgi için bkz. [komut satırında C/C++ derleme kodu](../../build/building-on-the-command-line.md).

Ml64.exe komut satırı seçenekleri hakkında daha fazla bilgi için bkz: [ML ve ML64 komut satırı başvurusu](../../assembler/masm/ml-and-ml64-command-line-reference.md).

Satır içi Birleştirici veya ASM anahtar x64 veya ARM hedefleri için desteklenmiyor. Bağlantı noktası, x86 bu kullanan satır içi derleyici kodu x64 veya ARM için C++ için kod dönüştürmek, derleyici iç bilgileri veya kullanabilirsiniz Çevirici dil kaynak dosyaları oluşturma. Visual C++ derleyici iç bilgileri ayrıcalıklı, örneğin, tarama ve test, birbirine kenetlenmiş vb., içinde olarak bir platformlar arası şekilde mümkün olduğunca yakın bit işlevi özel yönergeler kullanmanıza olanak tanımak için destekler. Kullanılabilir yapı içleri hakkında daha fazla bilgi için bkz: [derleyici iç bilgileri](../../intrinsics/compiler-intrinsics.md).

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>Bir Visual C++ projesine bir çevirici dili dosyası ekleme

Visual Studio Proje sistemi, C++ projelerinizde MASM kullanılarak oluşturulan Çevirici dil dosyalarını destekler. Çevirici dili kaynak dosyaları ve tam olarak x64 destekleyen MASM kullanarak nesne dosyalarına yapı x64 oluşturabilirsiniz. Bu nesne dosyaları için x64 yerleşik C++ kodunuzu ardından bağlanabilirsiniz hedefler. X x64 eksikliği çözmenin bir yolu budur satır içi derleyici.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>Varolan bir Visual C++ projesine bir çevirici dili dosyası eklemek için

1. Projede seçin **Çözüm Gezgini**. Menü çubuğunda, **proje**, **yapı özelleştirmeleri**.

1. İçinde **Visual C++ yapı özelleştirmesi dosyaları** iletişim kutusunda, yanındaki onay kutusunu işaretleyin **masm(.targets,.props)**. Seçin **Tamam** seçiminizi kaydetmek ve iletişim kutusunu kapatın.

1. Menü çubuğunda, **proje**, **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyası (.cpp)** Orta bölmedeki. İçinde **adı** düzen denetimi, olan yeni bir dosya adı girin. bir **.asm** .cpp yerine uzantısı. Seçin **Ekle** dosyayı projenize ekleyin ve iletişim kutusunu kapatın.

Çevirici dili kodunuzu eklediğiniz .asm dosyasına oluşturun. Çözümünüzü derleyin, ardından projenize bağlı olduğu bir nesne dosyasına .asm dosyasına derlemek için MASM derleyici çağrılır. Sembol erişimi kolaylaştırmak için derleyici işlevlerinizi olarak bildirin `extern "C"` C++ kaynak kodunuzda C++ kullanmak yerine Çevirici dili decoration kuralları kaynak dosyaları adlandırın.

## <a name="ml64-specific-directives"></a>ml64 özgü yönergeleri

Aşağıdaki ml64 özgü yönergeleri x64 hedefleyen Çevirici dil kaynak kodlarınızı kullanabilirsiniz:

- [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)

- [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)

- [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)

- [.PUSHREG](../../assembler/masm/dot-pushreg.md)

- [.SAVEREG](../../assembler/masm/dot-savereg.md)

- [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)

- [.SETFRAME](../../assembler/masm/dot-setframe.md)

Ayrıca, [PROC](../../assembler/masm/proc.md) yönergesi ml64.exe ile kullanmak için güncelleştirilmiştir.

## <a name="32-bit-address-mode-address-size-override"></a>32-bit adres modunu (adres boyutu geçersiz kılma)

Bir bellek işlenen 32-bit kayıtlarını içeriyorsa MASM 0x67 adres boyutu geçersiz kılma yayar. Örneğin, aşağıdaki örneklerde yayılan adres boyutu geçersiz kılma neden:

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

Bir 32-bit öteleme bellek işlenen olarak tek başına görünüyorsa, 64-bit adresleme düşünüldüğünü MASM varsayar. Şu anda 32-bit tür işlenenini çözmeye yönelik desteği yoktur.

Son olarak, aşağıdaki kodda gösterildiği gibi bir bellek işlenen içinde yazmaç boyutları karıştırma bir hata oluşturur.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>