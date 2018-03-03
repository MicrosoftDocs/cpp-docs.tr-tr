---
title: "Bildirim üretme komut satırında | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ba88017e0003c7a552c985516dba9a6254317a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-at-the-command-line"></a>Komut Satırında Bildirim Üretme
Bağlayıcı tüm nesne dosyaları işlenir ve son ikili yerleşik sonra nmake veya benzer araçlarını kullanarak komut satırından C/C++ uygulamaları oluştururken, bildirim oluşturulur. Bağlayıcı nesne dosyasında depolanan derleme bilgilerini toplar ve bu bilgileri son bildirim dosyası halinde birleştirir. Varsayılan olarak, bağlayıcı adlı bir dosya < binary_name > oluşturur. \<uzantısı > .manifest son ikili açıklanmaktadır. Bağlayıcı ikili içinde bildirim dosyası katıştırmak değil ve yalnızca bir bildirim dış dosyası olarak oluşturulmasına neden olabilir. Kullanarak gibi son ikili, bildirim eklemek için birkaç yol vardır [bildirim Aracı (mt.exe)](http://msdn.microsoft.com/library/aa375649) veya bir kaynak dosyasına bildirim derleme. İmzalama, artımlı bağlantılandırma, olarak gibi özellikleri etkinleştirmek için son ikili bildirim katıştırma zaman izlenmesi için belirli kurallar sahip göz önünde bulundurun ve Düzenle ve devam etmek önemlidir. Bunlar ve diğer seçenekleri ele alınmıştır [nasıl yapılır: bir bildirim içinde bir C/C++ uygulaması katıştırmak](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) komut satırında oluştururken.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bildirimleri](http://msdn.microsoft.com/library/aa375365)   
 [/ INCREMENTAL (artımlı Bağla)](../build/reference/incremental-link-incrementally.md)   
 [Tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue)   
 [C/C++ Programları Bildirim Üretimini Anlama](../build/understanding-manifest-generation-for-c-cpp-programs.md)