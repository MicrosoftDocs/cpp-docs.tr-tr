---
title: 'Nasıl yapılır: derleme MFC ve ATL kodu - clr kullanarak | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], interoperability
- ATL [C++], interoperability
- mixed assemblies [C++], MFC code
- mixed assemblies [C++], ATL code
- /clr compiler option [C++], compiling ATL and MFC code
- interoperability [C++], /clr compiler option
- regular MFC DLLs [C++], /clr compiler option
- interop [C++], /clr compiler option
- extension DLLs [C++], /clr compiler option
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7412d69230bcb6375a042d6cf8e8f27a3d9eac9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136073"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>Nasıl yapılır: /clr Kullanarak MFC ve ATL Kodu Derleme
Bu konu ortak dil çalışma zamanı hedeflemek için varolan MFC ve ATL programlarının nasıl yapılandırılabileceğini açıklar.  
  
### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>/ CLR kullanarak MFC yürütülebilir veya Normal MFC DLL'ine derlemek için  
  
1.  ' Nde projeye sağ **Çözüm Gezgini** ve ardından **özellikleri**.  
  
2.  İçinde **proje özelliklerini** iletişim kutusunda, yanına düğümünü **yapılandırma özellikleri** seçip **genel**. Sağ bölmede altında **Proje Varsayılanları**ayarlayın **ortak dil çalışma zamanı Destek** için **ortak dil çalışma zamanı desteği (/ clr)**.  
  
     Aynı bölmesinde olduğundan emin olun **kullanın, MFC** ayarlanır **MFC'yi paylaşılan DLL'de**.  
  
3.  Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Olduğundan emin olun **hata ayıklama bilgileri biçimi** ayarlanır **Program veritabanı /Zi** (değil **/zı**).  
  
4.  Seçin **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **yok (/ Gm-)**. Ayrıca **temel çalışma zamanı denetler** için **varsayılan**.  
  
5.  Altında **yapılandırma özellikleri**seçin **C/C++** ve ardından **kod oluşturma**. Olduğundan emin olun **çalışma zamanı kitaplığı** ayarlandığından **çok iş parçacıklı hata ayıklama DLL (/ MDd)** veya **çok iş parçacıklı DLL (/ MD)**.  
  
6.  Stdafx.h'de aşağıdaki satırı ekleyin.  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>/ CLR kullanarak MFC uzantı DLL'si derlemek için  
  
1.  "Bir MFC yürütülebilir veya Normal MFC DLL/CLR kullanarak derleme" adımları izleyin.  
  
2.  Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **önceden derlenmiş üstbilgiler**. Ayarlama **Oluştur/Kullan önceden derlenmiş üstbilgi** için **önceden derlenmiş üstbilgiler kullanılmıyor**.  
  
     Alternatif olarak, içinde **Çözüm Gezgini**, Stdafx.cpp sağ tıklayın ve ardından **özellikleri**. Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Ayarlama **ortak dil çalışma zamanı desteği ile Derle** için **ortak dil çalışma zamanı desteği yok**.  
  
3.  DllMain ve her şeyi içeren dosyası için buna çağırır **Çözüm Gezgini**, dosyaya sağ tıklayın ve ardından **özellikleri**. Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Sağ bölmede altında **Proje Varsayılanları**ayarlayın **ortak dil çalışma zamanı desteği ile Derle** için **ortak dil çalışma zamanı desteği yok**.  
  
### <a name="to-compile-an-atl-executable-by-using-clr"></a>/ CLR kullanarak ATL çalıştırılabilir derlemek için  
  
1.  İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**.  
  
2.  İçinde **proje özelliklerini** iletişim kutusunda, yanına düğümünü **yapılandırma özellikleri** seçip **genel**. Sağ bölmede altında **Proje Varsayılanları**ayarlayın **ortak dil çalışma zamanı Destek** için **ortak dil çalışma zamanı desteği (/ clr)**.  
  
3.  Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Olduğundan emin olun **hata ayıklama bilgileri biçimi** ayarlanır **Program veritabanı /Zi** (değil **/zı**).  
  
4.  Seçin **kod oluşturma** düğümü. Ayarlama **en az yeniden derlemeyi etkinleştir** için **yok (/ Gm-)**. Ayrıca **temel çalışma zamanı denetler** için **varsayılan**.  
  
5.  Altında **yapılandırma özellikleri**seçin **C/C++** ve ardından **kod oluşturma**. Olduğundan emin olun **çalışma zamanı kitaplığı** ayarlandığından **çok iş parçacıklı hata ayıklama DLL (/ MDd)** veya **çok iş parçacıklı DLL (/ MD)**.  
  
6.  Her MIDL oluşturulan dosyasının (C dosyaları), dosyayı sağ tıklatın **Çözüm Gezgini** ve ardından **özellikleri**. Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Ayarlama **ortak dil çalışma zamanı desteği ile Derle** için **ortak dil çalışma zamanı desteği yok**.  
  
### <a name="to-compile-an-atl-dll-by-using-clr"></a>/ CLR kullanarak ATL DLL derlemek için  
  
1.  "/ CLR kullanarak yürütülebilir bir ATL derlemek için" bölümündeki adımları izleyin.  
  
2.  Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **önceden derlenmiş üstbilgiler**. Ayarlama **Oluştur/Kullan önceden derlenmiş üstbilgi** için **önceden derlenmiş üstbilgiler kullanılmıyor**.  
  
     Alternatif olarak, içinde **Çözüm Gezgini**, Stdafx.cpp sağ tıklayın ve ardından **özellikleri**. Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Ayarlama **ortak dil çalışma zamanı desteği ile Derle** için **ortak dil çalışma zamanı desteği yok**.  
  
3.  DllMain ve her şeyi içeren dosyası için buna çağırır **Çözüm Gezgini**, dosyaya sağ tıklayın ve ardından **özellikleri**. Altında **yapılandırma özellikleri**, yanına düğümünü **C/C++** seçip **genel**. Sağ bölmede altında **Proje Varsayılanları**ayarlayın **ortak dil çalışma zamanı desteği ile Derle** için **ortak dil çalışma zamanı desteği yok**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)