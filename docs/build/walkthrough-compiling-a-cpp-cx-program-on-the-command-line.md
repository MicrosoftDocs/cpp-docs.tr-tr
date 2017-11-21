---
title: "İzlenecek yol: derleme C + +/ CX programı komut satırında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e3ae72f5f8cd268bae88a0b5f0be74864317ad0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CX Programı Derleme
Windows çalışma zamanı hedef ve komut satırında derleme Visual C++ programları oluşturabilirsiniz. Visual C++, Visual C++ bileşen uzantıları destekler (C + +/ CX), Windows çalışma zamanı programlama modeli hedeflemek için ek türleri ve işleçler sahiptir. Kullanabileceğiniz C + +/ CX Windows Phone 8.1, Windows mağazası ve Windows Masaüstü için uygulamalar oluşturmak için. Daha fazla bilgi için bkz: [A Tur, c + +/ CX](http://msdn.microsoft.com/magazine/dn166929.aspx) ve [çalışma zamanı platformları için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md).  
  
 Bu kılavuzda, temel C + oluşturmak için bir metin düzenleyicisi kullanın +/ CX programı ve komut satırında derleme. (Kullanabileceğiniz kendi C + +/ CX programı gösterilen bir yazmak yerine veya kullanabilirsiniz C + +/ CX kod örnekten başka bir Yardım makalesi. Bu teknik oluşturma ve hiçbir kullanıcı Arabirimi öğeleri içeren küçük modülleri sınamak için kullanışlıdır.)  
  
> [!NOTE]
>  C + derlemek için Visual Studio IDE kullanabilirsiniz +/ CX programlar. Tasarım, hata ayıklama, öykünme ve komut satırında kullanılamaz dağıtım desteği IDE içerdiği için Windows mağazası uygulamaları oluşturmak için IDE kullanmanızı öneririz. Daha fazla bilgi için bkz: [temel bir C++ mağazası uygulaması oluşturma](http://msdn.microsoft.com/library/windows/apps/dn263168).  
  
## <a name="prerequisites"></a>Önkoşullar  
 C++ dil temelleri anlamanız gerekir.  
  
## <a name="compiling-a-ccx-program"></a>Derleme C + +/ CX programı  
 Derleme için C + etkinleştirmek için +/ CX, kullanmalıdır [/ZW](../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği. Visual C++ derleyicisi Windows çalışma zamanı hedefler ve gerekli kitaplıklar bağlantılar bir .exe dosyası oluşturur.  
  
#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>Derlenecek C + +/ CX uygulama komut satırında  
  
1.  Açık bir **Geliştirici komut istemi** penceresi. (Üzerinde **Başlat** penceresi açık **uygulamaları**. Açık **Visual Studio Araçları** sürümünüzün altında bir klasör [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]ve ardından **Geliştirici komut istemi** kısayol.) Bir geliştirici komut istemi penceresi açın hakkında daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md).  
  
     Yönetici kimlik bilgileri başarıyla bilgisayarın işletim sistemine ve yapılandırmasına bağlı olarak kod derlemek için gerekli. Komut İstemi penceresi bir yönetici olarak çalıştırmak için kısayol menüsünü açın **Geliştirici komut istemi** ve ardından **yönetici olarak çalıştır**.  
  
2.  Komut isteminde girin **not defteri basiccx.cpp**.  
  
     Seçin **Evet** sizden istendiğinde dosya oluşturulamadı.  
  
3.  Not Defteri'nde, bu satırları girin:  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  Menü çubuğunda seçin **dosya**, **kaydetmek**.  
  
     Windows çalışma zamanı kullanan bir Visual C++ kaynak dosyası oluşturdunuz [Platform ad alanı](../cppcx/platform-namespace-c-cx.md) ad alanı.  
  
5.  Komut isteminde girin **cl /EHsc /ZW basiccx.cpp/Link /SUBSYSTEM:CONSOLE**. Cl.exe derleyicisi bir .obj dosyasına kaynak kodu derler ve ardından basiccx.exe adlı bir yürütülebilir programı oluşturmak için bağlayıcı çalıştırır. ( [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneği C++ özel durum işleme modeli belirtir ve [/link](../build/reference/link-pass-options-to-linker.md) bayrak bir konsol uygulaması belirtir.)  
  
6.  Komut isteminde basiccx.exe programı çalıştırmak için şunu girin **basiccx**.  
  
     Bu metin program görüntüler ve çıkar:  
  
    ```Output  
    This is a C++/CX program.  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)   
 [Derleyici Seçenekleri](../build/reference/compiler-options.md)