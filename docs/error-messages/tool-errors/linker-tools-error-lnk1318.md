---
title: Bağlayıcı araçları hatası LNK1318 | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1318
dev_langs:
- C++
helpviewer_keywords:
- LNK1318
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364c819c6ec2bf6e1195011eced6e6ad1699877b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570907"
---
# <a name="linker-tools-error-lnk1318"></a>Bağlayıcı araçları hatası LNK1318

> Beklenmeyen PDB hata; *neden* '*ayrıntıları*'

Bağlayıcı açarken, okuma veya PDB dosyasına yazılırken beklenmeyen bir hatayla karşılaştı.

Bu hata iletisini PDB dosyalarını seyrek sorunları için oluşturulur. *Neden* ve *ayrıntıları* hatanın oluştuğu sırada kullanılabilir bilgi bağlayıcıya temsil eder. Bu olarak PDB dosyalarını postalarla ayrı, daha bilgilendirici hata iletileri olduğunda yaygın hatalar, çok kullanışlı olabilir.

Hatanın kaynağını seyrek, olmadığından yalnızca genel öneriler bu sorunu çözümlemek için kullanılabilir:

- Yapı dizinlerinizi temiz bir işlemi gerçekleştirmek ve ardından tam bir yapı çözümünüzün yapın.

- Bilgisayarınızı yeniden başlatın veya parazit veya askıdaki mspdbsrv.exe işlemleri için denetleyin ve Görev Yöneticisi sonlandırın.

- Proje dizinlerinizi virüsten koruma denetimlerinde kapatın.

- Kullanım [/Zf](../../build/reference/zf.md) kullanıyorsanız derleyici seçeneği [/MP](../../build/reference/mp-build-with-multiple-processes.md) MSBuild veya başka bir paralel derleme işlemi.

- Yapı 64-bit barındırılan bir araç takımı kullanarak deneyin.

- Gerekirse paralel bağlantı sorunları gidermek için bağlama serileştirir. Mspdbsrv.exe bağlantı bir örneği tarafından başlatılır ve başka bir örneği bağlantı yapılır önce kapatılır bu hataya neden kullanıyor. Bu düzeltmeyi dezavantajı, proje derlemeleriniz tamamlamak için oldukça uzun sürebilir ' dir.