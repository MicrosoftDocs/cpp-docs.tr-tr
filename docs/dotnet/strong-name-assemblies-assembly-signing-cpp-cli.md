---
title: Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: ac46d069ece3c75af93f93497169d054b45267d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384588"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>Tanımlayıcı Ad Derlemeleri (Derleme İmzalama) (C++/CLI)

Bu konuda, genellikle derlemenizin güçlü bir isim verilmesi olarak adlandırılan derlemenizi nasıl oturum anlatılmaktadır.

## <a name="remarks"></a>Açıklamalar

Visual C++ kullanırken, derleme imzalama için CLR öznitelikleri için ilgili sorunlardan kaçınmak için bir derlemeyi imzalamak için bağlayıcı seçenekleri kullanın:

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

Anahtar adı, dosya adı, gizli bilgileri içeriyorsa, bir güvenlik riski olabilecek derleme metaverisine yerleştirilmez görünür hale öznitelikleri kullanmayan nedenleri içerir. Ayrıca, Visual C++ geliştirme ortamı tarafından kullanılan yapı işleminin bir derlemeyi bir katı ad vermek için CLR öznitelikleri kullanın ve ardından derleme üzerinde mt.exe gibi işlem sonrası bir araç çalıştırın, derleme imzalanır anahtarı geçersiz kılar.

Komut satırında derleme, bağlayıcı seçenekleri, derlemeyi imzalamak için kullanın ve ardından bir işlem sonrası Aracı (mt.exe gibi) çalıştırın, derleme sn.exe ile yeniden imzalamanız gerekecektir. Alternatif olarak, derleyebilir ve derleme oturum gecikme ve işlem sonrası araçları çalıştırdıktan sonra imzalama tamamlayın.

Geliştirme ortamında oluştururken imzalama öznitelikler kullanıyorsa, başarıyla derleme açıkça sn.exe çağırarak oturum ([Sn.exe (tanımlayıcı ad aracı)](/dotnet/framework/tools/sn-exe-strong-name-tool)) derleme sonrası olay. Daha fazla bilgi için [derleme olayları belirtme](../build/specifying-build-events.md). Öznitelikler ve bağlayıcı seçenekleri kullanmaya kıyasla bir derleme sonrası olay kullanıyorsanız derleme zamanlarını daha az olabilir.

Derleme imzalama aşağıdaki bağlayıcı seçenekleri destekler:

- [/DELAYSIGN (Derlemeyi Kısmen İmzala)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Tanımlayıcı derlemeler hakkında daha fazla bilgi için bkz. [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies).

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
