---
title: Projeleri Karışık Moddan Saf Ara Dile Dönüştürme
ms.date: 11/04/2016
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
ms.openlocfilehash: 93eff646fb582e25ad70549afc714c5321e56079
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328590"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Projeleri karışık moddan saf Ara dile dönüştürme

Tüm Visual C++ CLR projeleri için C çalışma zamanı kitaplıkları, varsayılan olarak bağlayın. Sonuç olarak, bu projeler, ortak dil çalışma zamanı (yönetilen kod için) hedefleyen kod ile yerel kod birleştirdiğinden karışık mod uygulamaları olarak sınıflandırılır. Bunlar derlenir, bunlar Ara dile (IL) olarak da bilinen Microsoft Ara dilini (MSIL) derlenir.

> [!IMPORTANT]
> Visual Studio 2015 kullanım dışı ve Visual Studio 2017 artık oluşturulmasını destekler **/CLR: pure** veya **/CLR: safe** CLR uygulamaları için kod. Saf veya güvenli derlemeleri ihtiyacınız varsa, uygulamanız için C# Çevir öneririz.

Destekleyen Visual C++ Derleyici Araç Takımı'nın önceki bir sürümünü kullanıyorsanız **/CLR: pure** veya **/CLR: safe**, kodunuzu saf MSIL olarak dönüştürmek için bu yordamı kullanın:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Karma mod uygulamanızı saf Ara dile dönüştürme

1. Bağlantıları Kaldır [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md) (CRT):

   1. .Cpp dosyasında giriş noktasını değiştirmek, uygulamanın giriş noktasını tanımlayan `Main()`. Kullanarak `Main()` projeniz için CRT bağlanmazsa gösterir.

   2. Çözüm Gezgini'nde projenize sağ tıklayıp **özellikleri** uygulamanız için özellik sayfalarını açmak için kısayol menüsünde.

   3. İçinde **Gelişmiş** proje özellik sayfası için **bağlayıcı**seçin **giriş noktası** ve enter **ana** bu alana.

   4. Konsol uygulamaları için de **sistem** proje özellik sayfası için **bağlayıcı**seçin **alt** alan ve değiştirmek için bu **konsol (/ Subsystem:Console)**.

      > [!NOTE]
      > Windows Forms uygulamaları için bu özelliği gerekmez **alt** ayarlanmış **Windows (/ alt sistemi: WINDOWS)** varsayılan olarak.

   5. Stdafx.h içinde tüm açıklama `#include` deyimleri. Konsol uygulamaları örneğin:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       veya

       Örneğin, Windows Forms uygulamalarında:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Windows Forms uygulamalarında Form1.cpp, açıklama için `#include` windows.h başvuran deyimi. Örneğin:

      ```cpp
      // #include <windows.h>
      ```

2. Stdafx.h için aşağıdaki kodu ekleyin:

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. Tüm yönetilmeyen türlerini kaldırın:

   Uygun yerlerde yapılarının başvuruları yönetilmeyen türler yerine [sistem](/dotnet/api/system) ad alanı. Ortak yönetilen türleri aşağıdaki tabloda listelenmiştir:

   |Yapı|Açıklama|
   |---------------|-----------------|
   |[Boole değeri](/dotnet/api/system.boolean)|Bir Boolean değeri temsil eder.|
   |[Bayt](/dotnet/api/system.byte)|Bir 8 bit işaretsiz tamsayıyı temsil eder.|
   |[Char](/dotnet/api/system.char)|Bir Unicode karakteri temsil eder.|
   |[Tarih/saat](/dotnet/api/system.datetime)|Anlık, genellikle bir tarih ve saat olarak ifade edilen zaman içinde temsil eder.|
   |[Ondalık](/dotnet/api/system.decimal)|Ondalık sayıyı temsil eder.|
   |[çift](/dotnet/api/system.double)|Çift duyarlıklı kayan nokta numarasını temsil eder.|
   |[GUID](/dotnet/api/system.guid)|Bir genel benzersiz tanıtıcısı (GUID) temsil eder.|
   |[Int16](/dotnet/api/system.int16)|Bir 16 bit işaretli tamsayıyı temsil eder.|
   |[Int32](/dotnet/api/system.int32)|32-bit imzalı bir tamsayı temsil eder.|
   |[Int64](/dotnet/api/system.int64)|64-bit imzalı bir tamsayı temsil eder.|
   |[IntPtr](/dotnet/api/system.intptr)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|
   |[SByte](/dotnet/api/system.byte)|Bir 8 bit işaretli tamsayıyı temsil eder.|
   |[Tek](/dotnet/api/system.single)|Tek duyarlıklı kayan nokta numarasını temsil eder.|
   |[TimeSpan](/dotnet/api/system.timespan)|Bir zaman aralığını temsil eder.|
   |[UInt16](/dotnet/api/system.uint16)|Bir 16 bit işaretsiz tamsayıyı temsil eder.|
   |[UInt32](/dotnet/api/system.uint32)|Bir 32-bit işaretsiz tamsayıyı temsil eder.|
   |[UInt64](/dotnet/api/system.uint64)|Bir 64-bit işaretsiz tamsayıyı temsil eder.|
   |[UIntPtr](/dotnet/api/system.uintptr)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|
   |[Geçersiz kılma](/dotnet/api/system.void)|Bir değer döndürmeyen bir yöntem gösterir. diğer bir deyişle, yöntemin void dönüş türüne sahip.|