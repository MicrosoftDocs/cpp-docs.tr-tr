---
title: "Nasıl yapılır: Windows 10 SDK 'Yı bir Windows masaüstü uygulamasında kullanma"
ms.custom: get-started-article
ms.date: 07/12/2018
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: 8dbf18d24c0369507743c3c1da624838f9ab4703
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513825"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Nasıl yapılır: Windows 10 SDK 'Yı bir Windows masaüstü uygulamasında kullanma

Visual Studio 2017 ' de klasik bir Windows Masaüstü projesi oluşturduğunuzda, C++ masaüstü iş yükü yüklenirken veya en son güncelleştirildiği sırada yüklenen WINDOWS 10 SDK sürümü ile oluşturmak için varsayılan olarak ayarlanır. Windows SDK bu sürümü Windows 7 ve üzeri sürümlerle uyumludur. Belirli Windows sürümlerini hedefleme hakkında daha fazla bilgi için bkz. [Windows üst bilgilerini kullanma](/windows/win32/WinProg/using-the-windows-headers) .

SDK 'nın önceki bir sürümünü hedeflemek istiyorsanız **projeyi açabilirsiniz | Özellikler** ve Windows SDK sürüm açılan menüsünde bulunan DIĞER SDK sürümlerinden seçim yapın.

Visual Studio 2015 ve Windows 10 SDK ile başlayarak, CRT kitaplığı, Evrensel Windows uygulamalarında kullanılması kabul edilebilir işlevleri içeren bir (ucrtbase), diğeri de (vcruntime140) olan her şeyi içeren iki parçaya ayrılmıştır. Windows 10 SDK, çok C99 işlevleri gibi yeni işlevler içerdiğinden, bu işlevleri kullanabilmeniz için bu adımları izlemeniz gerekir. Bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK 'sını hedeflemek için

1. Windows 10 SDK 'nın yüklü olduğundan emin olun. Windows 10 SDK, iş yüküyle **Masaüstü geliştirmenin C++**  bir parçası olarak yüklenir. [Windows 10 Için indirmeler ve araçlar](https://developer.microsoft.com/windows/downloads)'da tek başına sürüm kullanılabilir.

2. Proje düğümü için kısayol menüsünü açın ve **SDK sürümünü yeniden hedefle**' yi seçin.

   ![SDK sürümünü yeniden hedefle](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")

   **Çözüm eylemlerini gözden geçir** iletişim kutusu görüntülenir.

   ![Çözüm eylemlerini gözden geçirme](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

3. **Hedef platform sürümü** açılan listesinde, hedeflemek istediğiniz WINDOWS 10 SDK sürümünü seçin. Değişikliği uygulamak için Tamam düğmesini seçin.

   Bu bağlamdaki 8,1, Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 ve Windows Vista ile de backwardly uyumlu olan Windows SDK sürümüne başvurur.

   Bu adım başarılı olursa, çıkış penceresinde aşağıdaki metin görüntülenir:

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

4. Proje özelliklerini açın ve **yapılandırma özellikleri, genel** bölümünde **Windows hedef platformu sürümü**değerlerini görürsünüz. Burada değeri değiştirmek, bu yordamın takip eden etkile aynı etkiye sahiptir. Bkz. [genel özellik sayfası (proje)](../build/reference/general-property-page-project.md).

   ![Hedef platform sürümü](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   Bu eylem, üstbilgi dosyalarına ve kitaplık dosyalarına yollar içeren proje makrolarının değerlerini değiştirir. Nelerin değiştiğini görmek için, **Proje özellikleri** iletişim kutusunun **görsel C++ dizinler** bölümünde, **içerme dizinleri**gibi özelliklerden birini seçin, açılan listeyi açmak için seçin ve > Düzenle ' yi seçin \<. **Dizinleri dahil et** iletişim kutusu görüntülenir.

   ![Dizinleri dahil et iletişim kutusu](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   **Makrolar > >** düğmesini seçin ve tüm yeni değerleri görmek için makrolar listesini Windows SDK makrolarına kaydırın.

   ![Windows SDK makrolar](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

5. Gerektiğinde diğer projeler için tekrarlayın ve çözümü yeniden derleyin.

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK 'sını hedeflemek için

1. Proje düğümü için kısayol menüsünü açın ve **SDK sürümünü yeniden hedefle**' yi seçin.

2. **Hedef platform sürümü** açılan listesinde **8,1**' yi seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü uygulamaları (görsel C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)