---
title: Kutulama (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4c513b0148e2553440e02f9b0d255a0d5750e2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372518"
---
# <a name="boxing-ccli"></a>Kutulama (C++/CLI)

Kutulama olan bir değer türü türüne dönüştürme işlemi `object` veya değer türü tarafından uygulanan herhangi bir arabirim türüne. Ortak dil çalışma zamanı (CLR) bir değer türünü kutu, değeri sarar. bir `System.Object` ve Yönetilen öbekte depolar. Kutudan çıkarma, değer türünü nesneden çıkarır. Örtük kutulama; kutudan çıkarma açıktır.

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Nasıl yapılır: Açık Şekilde İstek Paketleme](../dotnet/how-to-explicitly-request-boxing.md)|Açık şekilde istek paketleme bir değişken üzerinde açıklar.|
|[Nasıl yapılır: Değer Türleri Oluşturmak için gcnew Kullanma ve Örtük Kutulamayı Kullanma](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Nasıl kullanılacağını gösterir `gcnew` yönetilen, atık olarak toplanmış yığındaki yerleştirilebilir bir kutulanmış değer türü oluşturmak için.|
|[Nasıl yapılır: Açma](../dotnet/how-to-unbox.md)|Açma ve bir değer değiştirme işlemi gösterilmektedir.|
|[Standart Dönüştürmeler ve Örtük Kutulama](../dotnet/standard-conversions-and-implicit-boxing.md)|Standart bir dönüşüm kutulama gerektiren bir dönüştürme derleyici tarafından seçmiş gösterir.|
|[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C++ belgelerinin .NET programlama için üst düzey makale.|