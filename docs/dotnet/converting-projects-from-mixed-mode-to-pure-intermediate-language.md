---
title: Karışık mod saf Ara dile dönüştürme projelerden | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 263a90710d2103c4ea97e6c56da67d676ba7366b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222086"
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

   Uygun yerlerde yapılarının başvuruları yönetilmeyen türler yerine [sistem](https://msdn.microsoft.com/library/system.appdomainmanager.appdomainmanager.aspx) ad alanı. Ortak yönetilen türleri aşağıdaki tabloda listelenmiştir:

   |Yapı|Açıklama|
   |---------------|-----------------|
   |[Boole değeri](https://msdn.microsoft.com/library/system.boolean\(v=vs.140\).aspx)|Bir Boolean değeri temsil eder.|
   |[Bayt](https://msdn.microsoft.com/library/system.byte\(v=vs.140\).aspx)|Bir 8 bit işaretsiz tamsayıyı temsil eder.|
   |[Char](https://msdn.microsoft.com/library/system.char\(v=vs.140\).aspx)|Bir Unicode karakteri temsil eder.|
   |[Tarih/saat](https://msdn.microsoft.com/library/system.datetime.datetime.aspx)|Anlık, genellikle bir tarih ve saat olarak ifade edilen zaman içinde temsil eder.|
   |[Ondalık](https://msdn.microsoft.com/library/system.decimal\(v=vs.140\).aspx)|Ondalık sayıyı temsil eder.|
   |[çift](https://msdn.microsoft.com/library/system.double\(v=vs.140\).aspx)|Çift duyarlıklı kayan nokta numarasını temsil eder.|
   |[GUID](https://msdn.microsoft.com/library/system.guid\(v=vs.140\).aspx)|Bir genel benzersiz tanıtıcısı (GUID) temsil eder.|
   |[Int16](https://msdn.microsoft.com/library/system.int16\(v=vs.140\).aspx)|Bir 16 bit işaretli tamsayıyı temsil eder.|
   |[Int32](https://msdn.microsoft.com/library/system.int32\(v=vs.140\).aspx)|32-bit imzalı bir tamsayı temsil eder.|
   |[Int64](https://msdn.microsoft.com/library/system.int64\(v=vs.140\).aspx)|64-bit imzalı bir tamsayı temsil eder.|
   |[IntPtr](https://msdn.microsoft.com/library/system.intptr\(v=vs.140\).aspx)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|
   |[SByte](https://msdn.microsoft.com/library/system.byte.aspx)|Bir 8 bit işaretli tamsayıyı temsil eder.|
   |[Tek](https://msdn.microsoft.com/library/system.single.aspx)|Tek duyarlıklı kayan nokta numarasını temsil eder.|
   |[Zaman aralığı](https://msdn.microsoft.com/library/system.timespan\(v=vs.140\).aspx)|Bir zaman aralığını temsil eder.|
   |[UInt16](https://msdn.microsoft.com/library/system.uint16\(v=vs.140\).aspx)|Bir 16 bit işaretsiz tamsayıyı temsil eder.|
   |[UInt32](https://msdn.microsoft.com/library/system.uint32\(v=vs.140\).aspx)|Bir 32-bit işaretsiz tamsayıyı temsil eder.|
   |[UInt64](https://msdn.microsoft.com/library/system.uint64\(v=vs.140\).aspx)|Bir 64-bit işaretsiz tamsayıyı temsil eder.|
   |[UIntPtr](https://msdn.microsoft.com/library/system.uintptr\(v=vs.140\).aspx)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|
   |[Geçersiz kılma](https://msdn.microsoft.com/library/system.void\(v=vs.140\).aspx)|Bir değer döndürmeyen bir yöntem gösterir. diğer bir deyişle, yöntemin void dönüş türüne sahip.|