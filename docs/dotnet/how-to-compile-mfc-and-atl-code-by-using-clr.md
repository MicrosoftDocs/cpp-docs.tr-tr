---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır:/clr kullanarak MFC ve ATL kodu derleme'
title: Nasıl yapılır:-clr kullanarak MFC ve ATL kodu derleme
ms.custom: get-started-article
ms.date: 11/04/2016
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
ms.openlocfilehash: 67a861dac3b4c4b454f4fbde4a500c3677ce0e25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304499"
---
# <a name="how-to-compile-mfc-and-atl-code-by-using-clr"></a>Nasıl yapılır: /clr Kullanarak MFC ve ATL Kodu Derleme

Bu konuda, var olan MFC ve ATL programlarının ortak dil çalışma zamanını hedeflemek için nasıl derlenmesi anlatılmaktadır.

### <a name="to-compile-an-mfc-executable-or-regular-mfc-dll-by-using-clr"></a>/Clr kullanarak bir MFC yürütülebilir dosyası veya normal MFC DLL derlemek için

1. **Çözüm Gezgini** ' de projeye sağ tıklayın ve ardından **Özellikler**' e tıklayın.

1. **Proje özellikleri** Iletişim kutusunda **yapılandırma özellikleri** ' nin yanındaki düğümü genişletin ve **genel**' i seçin. Sağ bölmede, **Proje Varsayılanları** altında ortak dil çalışma **zamanı** desteğini **ortak dil çalışma zamanı desteği (/CLR)** olarak ayarlayın.

   Aynı bölmede, **MFC kullanmanın** **paylaşılan BIR DLL 'de MFC kullanacak** şekilde ayarlandığından emin olun.

1. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. **Hata ayıklama bilgi biçiminin** , **Program veritabanı/Zi** ( **/Zi** değil) olarak ayarlandığından emin olun.

1. **Kod oluşturma** düğümünü seçin. **En az yeniden derlemeyi etkinleştir** **(/GM-)** olarak ayarlayın. **Temel çalışma zamanı denetimlerini** de **varsayılan** olarak ayarlayın.

1. **Yapılandırma özellikleri** altında **C/C++** ve sonra **kod oluşturma**' yı seçin. **Çalışma zamanı kitaplığının** **çok Iş PARÇACıKLı hata ayıklama dll (/MDD)** veya **çok iş parçacıklı DLL (/MD)** olarak ayarlandığından emin olun.

1. Stbafx. h içinde aşağıdaki satırı ekleyin.

    ```
    #using <System.Windows.Forms.dll>
    ```

### <a name="to-compile-an-mfc-extension-dll-by-using-clr"></a>/Clr kullanarak bir MFC uzantısı DLL derlemek için

1. "/Clr kullanarak MFC yürütülebilir dosyası veya normal MFC DLL derlemek Için" bölümündeki adımları izleyin.

1. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **önceden derlenmiş üst bilgiler**' i seçin. Önceden derlenmiş **üst bilgileri kullanmadan** **önceden derlenmiş üst bilgi oluştur/kullan** öğesini ayarlayın.

   Alternatif olarak, **Çözüm Gezgini**, Stdadfx. cpp öğesine sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. Ortak dil **çalışma zamanı desteği olmayan** **ortak dil çalışma zamanı desteğiyle derlemeyi** ayarlayın.

1. DllMain içeren dosya ve çağrı yaptığı her şey için, **Çözüm Gezgini**, dosyaya sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. Sağ bölmede, **Proje Varsayılanları** altında, ortak dil çalışma zamanı desteği **ile derlemeyi ortak** dil **çalışma zamanı desteği olmadan** ayarlayın.

### <a name="to-compile-an-atl-executable-by-using-clr"></a>/Clr kullanarak ATL yürütülebilirini derlemek için

1. **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **Özellikler**' e tıklayın.

1. **Proje özellikleri** Iletişim kutusunda **yapılandırma özellikleri** ' nin yanındaki düğümü genişletin ve **genel**' i seçin. Sağ bölmede, **Proje Varsayılanları** altında ortak dil çalışma **zamanı** desteğini **ortak dil çalışma zamanı desteği (/CLR)** olarak ayarlayın.

1. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. **Hata ayıklama bilgi biçiminin** , **Program veritabanı/Zi** ( **/Zi** değil) olarak ayarlandığından emin olun.

1. **Kod oluşturma** düğümünü seçin. **En az yeniden derlemeyi etkinleştir** **(/GM-)** olarak ayarlayın. **Temel çalışma zamanı denetimlerini** de **varsayılan** olarak ayarlayın.

1. **Yapılandırma özellikleri** altında **C/C++** ve sonra **kod oluşturma**' yı seçin. **Çalışma zamanı kitaplığının** **çok Iş PARÇACıKLı hata ayıklama dll (/MDD)** veya **çok iş parçacıklı DLL (/MD)** olarak ayarlandığından emin olun.

1. Her MıDL tarafından oluşturulan dosya (C dosyaları) için **Çözüm Gezgini** ' de dosyaya sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. Ortak dil **çalışma zamanı desteği olmayan** **ortak dil çalışma zamanı desteğiyle derlemeyi** ayarlayın.

### <a name="to-compile-an-atl-dll-by-using-clr"></a>/Clr kullanarak ATL DLL derlemek için

1. "/Clr kullanarak ATL yürütülebilirini derlemek Için" bölümündeki adımları izleyin.

1. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **önceden derlenmiş üst bilgiler**' i seçin. Önceden derlenmiş **üst bilgileri kullanmadan** **önceden derlenmiş üst bilgi oluştur/kullan** öğesini ayarlayın.

   Alternatif olarak, **Çözüm Gezgini**, Stdadfx. cpp öğesine sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. Ortak dil **çalışma zamanı desteği olmayan** **ortak dil çalışma zamanı desteğiyle derlemeyi** ayarlayın.

1. DllMain içeren dosya ve çağrı yaptığı her şey için, **Çözüm Gezgini**, dosyaya sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Yapılandırma özellikleri** altında **C/C++** ' ın yanındaki düğümü genişletin ve **genel**' i seçin. Sağ bölmede, **Proje Varsayılanları** altında, ortak dil çalışma zamanı desteği **ile derlemeyi ortak** dil **çalışma zamanı desteği olmadan** ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
