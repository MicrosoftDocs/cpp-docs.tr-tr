---
title: "MASM için x64 (ml64.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1f4caa98eecc2a7bcdebe7540b17842ea972725
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="masm-for-x64-ml64exe"></a>x64 (ml64.exe) için (MASM)

Visual Studio 32-bit ve 64-bit barındırılan sürümlerine MASM hedef x64 kodu içerir. Ml64.exe adlı, x64 kabul assembler budur assembler dili. Visual Studio yükleme sırasında bir C++ iş yükü seçtiğinizde MASM komut satırı araçları yüklenir. Bu araçları ayrı bir yükleme olarak kullanılamaz. Karşıdan yükle ve Visual Studio bir kopyasını yüklemek için bkz: [https://www.visualstudio.com/](https://www.visualstudio.com/). Visual Studio IDE yüklemek istediğiniz değil ancak yalnızca komut satırı araçlarını istiyorsanız bkz **derleme araçları Visual Studio 2017 için** seçeneği [Visual Studio indirmeleri](https://www.visualstudio.com/downloads/) sayfası.

MASM oluşturmak için kullanılacak x64 kodunu hedefler komut satırında, x64 için geliştirici komut istemi kullanın gerekli yolu ve diğer ortam değişkenlerini ayarlar hedefler. Bir geliştirici komut istemi başlatmak hakkında daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../../build/building-on-the-command-line.md).

Ml64.exe komut satırı seçenekleri hakkında daha fazla bilgi için bkz: [ML ve ML64 komut satırı başvurusu](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
Satır içi derleyicisi veya ASM anahtar kullanımını x64 veya ARM hedefleri için desteklenmiyor. Bağlantı noktası için bu kullanımları satır içi derleyicisi, x86 kodu x64 veya ARM için kodunuzu C++ olarak dönüştürme, derleyici iç bilgileri veya kullanabilirsiniz assembler dili kaynak dosyaları oluşturun. Visual C++ derleyici iç bilgileri ayrıcalıklı, örneğin, tarama ve test, ınterlocked ve vb. içinde olarak bir platformlar arası şekilde mümkün olduğunca yakın bit için özel işlevi yönergeleri kullanmanıza izin veren destekler. Kullanılabilir iç bilgileri hakkında daha fazla bilgi için bkz: [derleyici iç bilgileri](../../intrinsics/compiler-intrinsics.md).  

## <a name="add-an-assembler-language-file-to-a-visual-c-project"></a>Visual C++ projeye assembler dil dosya ekleme  
  
Visual Studio Proje sistemi C++ projelerinde MASM kullanılarak oluşturulmuş assembler dil dosyalarını destekler. Derleyici dil kaynak dosyaları ve bunları x64 tamamen destekler MASM kullanarak nesne dosyalarıyla yapı x64 oluşturabilirsiniz. Bu nesne dosyaları x64 için yerleşik C++ kodunuzu sonra bağlayabilirsiniz hedefler. X x64 eksikliği çözmenin bir yolu budur satır içi derleyicisi.  

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-c-project"></a>Varolan bir Visual C++ projesine bir assembler dil dosyası eklemek için

1. Projede seçin **Çözüm Gezgini**. Menü çubuğunda seçin **proje**, **derleme özelleştirmeleri**.

1. İçinde **Visual C++ derleme özelleştirme dosyaları** iletişim kutusunda, yanındaki onay kutusunu işaretleyin **masm(.targets,.props)**. Seçin **Tamam** seçiminizi kaydetmek ve iletişim kutusunu kapatın.

1. Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**. 

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyasına (.cpp)** Orta bölmede. İçinde **adı** düzen denetimi, sahip yeni bir dosya adı girin bir **.asm** .cpp yerine uzantısı. Seçin **Ekle** dosyayı projenize ekleyin ve iletişim kutusunu kapatın.

Derleyici dil kodunuzu eklediğiniz .asm dosyasında oluşturun. Çözümünüzü yapılandırdığınızda MASM derleyici projenize sonra bağlı olduğu bir nesne dosyasına .asm dosya derlemek için çağrılır. Sembol erişimi kolaylaştırmak için assembler işlevlerinizi olarak bildirme `extern "C"` , C++ kaynak kodu C++ kullanmak yerine, assembler dilde decoration kuralları kaynak dosyaları adı.
  
## <a name="ml64-specific-directives"></a>ml64 özgü yönergeleri  

Aşağıdaki ml64 özgü yönergeleri x64 hedefleyen assembler dili kaynak kodunuzda kullanabilirsiniz:  
  
-   [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [. ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [. PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [. PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [. SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [. SETFRAME](../../assembler/masm/dot-setframe.md)  
  
Ayrıca, [PROC](../../assembler/masm/proc.md) yönergesi ml64.exe ile kullanılmak üzere güncelleştirilmiştir.  
  
## <a name="32-bit-address-mode-address-size-override"></a>32-bit adres modunu (adres boyutu geçersiz kılma)  

Bir bellek işlenen 32-bit kayıtları içeriyorsa MASM 0x67 adresini boyutu geçersiz kılma yayar. Örneğin, aşağıdaki örneklerde yayınlaması için adres boyutu geçersiz kılma neden:  
  
```MASM  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
32-bit öteleme bellek işleneni olarak tek başına görünürse, 64-bit adresleme düşünüldüğünü MASM varsayar. Şu anda bu tür işlenen 32-bit adresleme için destek yok.  
  
Son olarak, aşağıdaki kodda gösterildiği gibi bir bellek işlenen içinde kayıt boyutları karıştırma bir hata oluşturur.  
  
```MASM  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Microsoft Macro Assembler başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)