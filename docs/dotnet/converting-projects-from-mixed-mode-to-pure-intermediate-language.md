---
title: "Karışık mod saf Ara dile projelerden dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0276d5b5420ed0294b2cf3438190f79d03585744
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Projeleri Karışık Moddan Saf Ara Dile Dönüştürme
Tüm Visual C++ CLR projeleri için C çalışma zamanı kitaplıkları varsayılan olarak bağlayın. Sonuç olarak, ortak dil çalışma zamanı (yönetilen kod) hedefleyen kod ile yerel kod birleştirdiğinden bu projeleri karışık mod uygulamaları sınıflandırılır. Derlenmiş, bunlar Ara dile (IL) olarak da bilinen Microsoft Ara dili (MSIL) derlenir.  
  
### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Karışık mod uygulamanızı saf Ara dile dönüştürme  
  
1.  Bağlantılar kaldırmak [C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md) (CRT):  
  
    1.  .Cpp dosyasında giriş noktasını değiştirmek, uygulamanızın giriş noktası tanımlama `Main()`. Kullanarak `Main()` projeniz için CRT bağlanmazsa gösterir.  
  
    2.  Çözüm Gezgini'nde, projenize sağ tıklayın ve seçin **özellikleri** uygulamanız için özellik sayfalarını açmak için kısayol menüsünde.  
  
    3.  İçinde **Gelişmiş** proje özellik sayfasında **bağlayıcı**seçin **giriş noktası** yazıp enter **ana** bu alandaki.  
  
    4.  Konsol uygulamaları için de **sistem** proje özellik sayfasında **bağlayıcı**seçin **alt sistemi** alan ve bu değişiklik **konsol (/ Subsystem:Console)**.  
  
        > [!NOTE]
        >  Windows Forms uygulamaları için bu özelliği gerekmez **alt sistemi** alan ayarlanmış **Windows (/ alt sistemi: WINDOWS)** varsayılan olarak.  
  
    5.  Tüm Stdafx.h'de açıklama `#include` deyimleri. Örneğin, konsol uygulamaları:  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         veya  
  
         Örneğin, Windows Forms uygulamalarında:  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Windows Forms uygulamalarında Form1.cpp, çıkışı açıklama için `#include` windows.h başvuruyor deyimi. Örneğin:  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  Stdafx.h için aşağıdaki kodu ekleyin:  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  Tüm yönetilmeyen türler kaldırın:  
  
    1.  Uygun olduğunda, yönetilmeyen türler yapıları başvuruları değiştirin [sistem](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) ad alanı. Ortak yönetilen türleri aşağıdaki tabloda listelenmiştir:  
  
        |Yapı|Açıklama|  
        |---------------|-----------------|  
        |[Boole değeri](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Bir Boole değeri temsil eder.|  
        |[Bayt](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Bir 8 bit işaretsiz tamsayıyı temsil eder.|  
        |[Char](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Unicode karakteri temsil eder.|  
        |[Tarih saat](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Anlık, genellikle bir tarih ve saat ifade edilen, zaman içindeki temsil eder.|  
        |[Ondalık](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Ondalık bir sayı temsil eder.|  
        |[Çift](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Çift duyarlıklı kayan noktalı sayıyı temsil eder.|  
        |[GUID](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Bir genel benzersiz tanımlayıcı (GUID) temsil eder.|  
        |[Int16](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Bir 16 bit işaretli tamsayıyı temsil eder.|  
        |[Int32](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Bir 32 bit işaretli tamsayıyı temsil eder.|  
        |[Int64](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Bir 64-bit işaretli tamsayıyı temsil eder.|  
        |[IntPtr](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|  
        |[SByte](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Bir 8 bit işaretli tamsayıyı temsil eder.|  
        |[Tek](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Tek duyarlıklı kayan noktalı sayıyı temsil eder.|  
        |[TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Bir zaman aralığı temsil eder.|  
        |[UInt16](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Bir 16 bit işaretsiz tamsayıyı temsil eder.|  
        |[UInt32](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Bir 32 bit işaretsiz tamsayıyı temsil eder.|  
        |[UInt64](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Bir 64-bit işaretsiz tamsayıyı temsil eder.|  
        |[UIntPtr](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Bir işaretçi veya bir tanıtıcı temsil etmek için kullanılan bir platforma özgü türü.|  
        |[Geçersiz kılma](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Bir değer döndürmeyen bir yöntemi gösterir; diğer bir deyişle, yöntemin dönüş türü void vardır.|