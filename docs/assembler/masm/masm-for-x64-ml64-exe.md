---
description: 'Daha fazla bilgi edinin: x64 için Masd (ml64.exe)'
title: x64 (ml64.exe) için (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 58970f65fbd98b4cbebae0a36c615cb380ec5b75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129733"
---
# <a name="masm-for-x64-ml64exe"></a>x64 (ml64.exe) için (MASM)

Visual Studio, x64 kodunu hedeflemek için hem 32-bit hem de 64 Bit barındırılan Microsoft Assembler (Masd) sürümlerini içerir. Adlandırılmış ml64.exe, bu, x64 assembler dilini kabul eden bir derleyicisimdir. Visual Studio yüklemesi sırasında bir C++ iş yükü seçtiğinizde MASı komut satırı araçları yüklenir. Masa araçları ayrı bir indirme olarak kullanılamaz. Visual Studio 'nun bir kopyasını indirme ve yükleme hakkında yönergeler için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio). Visual Studio IDE 'nin tamamını yüklemek istemiyorsanız, ancak yalnızca komut satırı araçlarının yerine [Visual Studio Için derleme araçlarını](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)indirin.

Komut satırında x64 hedefleri için kod oluşturmak üzere Masd 'yi kullanmak için, gerekli yolu ve diğer ortam değişkenlerini ayarlayan x64 hedefleri için bir geliştirici komut istemi kullanmanız gerekir. Geliştirici komut istemi başlatma hakkında daha fazla bilgi için, bkz. [komut satırında C/C++ kodu oluşturma](../../build/building-on-the-command-line.md).

Komut satırı seçenekleri ml64.exe hakkında bilgi için bkz. [ml ve ML64 Command-Line başvurusu](ml-and-ml64-command-line-reference.md).

Satır içi assembler veya ASM anahtar sözcüğünün kullanımı x64 veya ARM hedefleri için desteklenmez. X64 veya ARM için satır içi assembler kullanan x86 kodunuzun bağlantı noktası için, kodunuzu C++ ' a dönüştürebilir, derleyici iç bilgileri kullanabilir veya assembler dili kaynak dosyaları oluşturabilirsiniz. Microsoft C++ derleyicisi, özel işlev yönergelerini (örneğin, ayrıcalıklı, bit tarama/test, birbirine kilitli vb.) kullanmanıza olanak tanımak için iç işlemleri destekler. Kullanılabilir iç bilgiler hakkında bilgi için bkz. [derleyici iç](../../intrinsics/compiler-intrinsics.md)bilgileri.

## <a name="add-an-assembler-language-file-to-a-visual-studio-c-project"></a>Visual Studio C++ projesine bir assembler dili dosyası ekleme

Visual Studio proje sistemi, C++ projelerinizde Masd kullanılarak oluşturulan assembler dili dosyalarını destekler. X64 birleştirici dil kaynak dosyaları oluşturabilir ve bunları x64 tam destekleyen Masd kullanarak nesne dosyalarında oluşturabilirsiniz. Daha sonra bu nesne dosyalarını, x64 hedefleri için oluşturulmuş C++ kodunuza bağlayabilirsiniz. Bu, bir x64 satır içi assembler eksikliğinden oluşan bir yoldur.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-studio-c-project"></a>Varolan bir Visual Studio C++ projesine bir assembler dili dosyası eklemek için

1. **Çözüm Gezgini** içinde projeyi seçin. Menü çubuğunda **Proje**, **Özelleştirmeleri oluştur**' u seçin.

1. **Visual C++ yapı özelleştirme dosyaları** iletişim kutusunda **ması (. targets,. props)** yanındaki onay kutusunu işaretleyin. Seçiminizi kaydetmek ve iletişim kutusunu kapatmak için **Tamam** ' ı seçin.

1. Menü çubuğunda **Proje**, **Yeni öğe Ekle**' yi seçin.

1. **Yeni öğe Ekle** iletişim kutusunda, Orta bölmede **C++ dosyası (. cpp)** öğesini seçin. **Ad** düzenleme denetiminde,. cpp yerine **. asm** uzantısına sahip yeni bir dosya adı girin. Dosyayı projenize eklemek için **Ekle** ' yi seçin ve iletişim kutusunu kapatın.

Eklediğiniz. asm dosyasında assembler dili kodunuzu oluşturun. Çözümünüzü oluştururken, MASı derleyicisi,. asm dosyasını, daha sonra projenize bağlanmış bir nesne dosyasına birleştirmek için çağrılır. Sembol erişimini daha kolay hale getirmek için, assembler `extern "C"` dili kaynak dosyalarınızda c++ ad düzenleme kurallarını kullanmak yerine, derleyici Işlevlerinizi c++ kaynak kodunuzda olarak bildirin.

## <a name="ml64-specific-directives"></a>ML64 'e özgü yönergeler

Aşağıdaki ML64 özgü yönergeleri, 64 ' i hedefleyen assembler dili kaynak kodunuzda kullanabilirsiniz:

- [.ALLOCSTACK](dot-allocstack.md)

- [.ENDPROLOG](dot-endprolog.md)

- [.PUSHFRAME](dot-pushframe.md)

- [.PUSHREG](dot-pushreg.md)

- [.SAVEREG](dot-savereg.md)

- [.SAVEXMM128](dot-savexmm128.md)

- [.SETFRAME](dot-setframe.md)

Ayrıca, [proc](proc.md) yönergesi ml64.exe ile kullanım için güncelleştirilmiştir.

## <a name="32-bit-address-mode-address-size-override"></a>32-bit adres modu (adres boyutu geçersiz kılma)

Bir bellek işleneni 32 bitlik Yazmaçları içeriyorsa, mask, 0x67 adres boyutu geçersiz kılmayı yayar. Örneğin, aşağıdaki örnekler adres boyutu geçersiz kılmanın oluşturulmasına neden olur:

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

Masa, 32 bitlik bir öteleme 'in tek başına bir bellek işleneni olarak göründüğünü varsayar, 64 bit adresleme amaçlıdır. Şu anda bu tür işlenenleri 32 bit adresleme desteği yoktur.

Son olarak, aşağıdaki kodda gösterildiği gibi, bir bellek işleneni içindeki kayıt boyutlarını karıştırma bir hata oluşturur.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](microsoft-macro-assembler-reference.md)
