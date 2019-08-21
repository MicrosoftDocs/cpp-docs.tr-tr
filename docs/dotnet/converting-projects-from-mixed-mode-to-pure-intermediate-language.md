---
title: Projeleri Karışık Moddan Saf Ara Dile Dönüştürme
ms.date: 08/19/2019
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
ms.openlocfilehash: 05ece23e6d79fc399085099deebcde0aa4a92c64
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630842"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Projeleri karışık moddan saf ara dile dönüştürme

Tüm Visual C++ clr projeleri varsayılan olarak C çalışma zamanı kitaplıklarına bağlanır. Sonuç olarak, bu projeler Karma modlu uygulamalar olarak sınıflandırılır çünkü yerel kodu ortak dil çalışma zamanını (yönetilen kod) hedefleyen kodla birleştirir. Derlendiklerinde, Microsoft ara dili (MSIL) olarak da bilinen ara dil (IL) olarak derlenir.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017, CLR uygulamaları için artık **/clr: Pure** veya **/clr: Safe** kodu oluşturulmasını desteklememektedir. Saf veya güvenli derlemelere ihtiyacınız varsa, uygulamanızı ' ye C#çevirmenizi öneririz.

**/Clr: Pure** veya **/clr: Safe**' i destekleyen C++ Microsoft derleyicisi araç takımının önceki BIR sürümünü kullanıyorsanız, kodunuzu saf MSIL 'e dönüştürmek için bu yordamı kullanabilirsiniz:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Karma mod uygulamanızı saf ara dile dönüştürmek için

1. [C çalışma zamanı kitaplıklarının](../c-runtime-library/crt-library-features.md) (CRT) bağlantılarını kaldırma:

   1. Uygulamanızın giriş noktasını tanımlayan. cpp dosyasında, giriş noktasını olarak `Main()`değiştirin. Kullanarak `Main()` , projenizin CRT ile bağlantı olmadığını gösterir.

   2. Çözüm Gezgini, projenize sağ tıklayın ve uygulamanızın özellik sayfalarını açmak için kısayol menüsünde **Özellikler** ' i seçin.

   3. **Bağlayıcının** **Gelişmiş** proje özelliği sayfasında, **giriş noktasını** seçin ve ardından bu alana **Main** yazın.

   4. Konsol uygulamaları için, **bağlayıcının** **sistem** projesi Özellik sayfasında **alt sistem** alanını seçin ve bunu **konsola değiştirin (/Subsystem: Console)** .

      > [!NOTE]
      > **Alt sistem** alanı varsayılan olarak **Windows (/Subsystem: Windows)** olarak ayarlandığından, bu özelliği Windows Forms uygulamalar için ayarlamanız gerekmez.

   5. *Stbafx. h*içinde, tüm `#include` deyimlerini açıklama olarak inceleyin. Örneğin, konsol uygulamalarında:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       -veya-

       Örneğin, Windows Forms uygulamalarda:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Windows Forms uygulamalar için, Form1. cpp içinde, Windows. h `#include` 'e başvuran ifadeyi açıklama olarak yapın. Örneğin:

      ```cpp
      // #include <windows.h>
      ```

2. Aşağıdaki kodu *stbafx. h*öğesine ekleyin:

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. Tüm yönetilmeyen türleri kaldır:

   Uygun olduğunda, yönetilmeyen türleri [sistem](/dotnet/api/system) ad alanındaki yapılar başvuruları ile değiştirin. Ortak yönetilen türler aşağıdaki tabloda listelenmiştir:

   |Yapı|Açıklama|
   |---------------|-----------------|
   |[Boole değeri](/dotnet/api/system.boolean)|Bir Boolean değeri temsil eder.|
   |[Bayt](/dotnet/api/system.byte)|8 bit işaretsiz tamsayıyı temsil eder.|
   |[Char](/dotnet/api/system.char)|Bir Unicode karakteri temsil eder.|
   |[Hem](/dotnet/api/system.datetime)|Genellikle günün tarih ve saati olarak ifade edilen bir anlık zamanı temsil eder.|
   |[Kategori](/dotnet/api/system.decimal)|Ondalık sayıyı temsil eder.|
   |[Çift](/dotnet/api/system.double)|Çift duyarlıklı kayan noktalı sayıyı temsil eder.|
   |['İni](/dotnet/api/system.guid)|Genel benzersiz tanımlayıcıyı (GUID) temsil eder.|
   |[Int16](/dotnet/api/system.int16)|16 bit işaretli tamsayıyı temsil eder.|
   |[Int32](/dotnet/api/system.int32)|32 bitlik işaretli bir tamsayıyı temsil eder.|
   |[Tutulamaz](/dotnet/api/system.int64)|64 bitlik işaretli bir tamsayıyı temsil eder.|
   |[IntPtr](/dotnet/api/system.intptr)|Bir işaretçiyi veya tanıtıcıyı temsil etmek için kullanılan platforma özgü bir tür.|
   |[SByte](/dotnet/api/system.byte)|8 bit işaretli tamsayıyı temsil eder.|
   |[Sunuculu](/dotnet/api/system.single)|Tek duyarlıklı kayan noktalı sayıyı temsil eder.|
   |[TimeSpan](/dotnet/api/system.timespan)|Bir zaman aralığını temsil eder.|
   |[Int16](/dotnet/api/system.uint16)|16 bit işaretsiz tamsayıyı temsil eder.|
   |[Int32](/dotnet/api/system.uint32)|32 bitlik işaretsiz bir tamsayıyı temsil eder.|
   |[Int64](/dotnet/api/system.uint64)|64 bitlik işaretsiz bir tamsayıyı temsil eder.|
   |[UIntPtr](/dotnet/api/system.uintptr)|Bir işaretçiyi veya tanıtıcıyı temsil etmek için kullanılan platforma özgü bir tür.|
   |[Kağıt](/dotnet/api/system.void)|Değer döndürmeyen bir yöntemi gösterir; diğer bir deyişle, yöntemin void dönüş türü vardır.|