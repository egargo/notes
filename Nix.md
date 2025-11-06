# Nix Notes

```nix
# Build Go module
let
    package = with pkgs; buildGoModule rec {
        pname = "package";
        version = "1.0.0";

        src = fetchFromGitHub {
            owner = "owner";
            repo = pname;
            rev = "v${version}";
            hash = "sha256-AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=";
        };

        vendorHash = "sha256-AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=";

        postPatch = ''
            # optionally remove tests
        '';

        meta = with lib; {
            description = "Description";
            homepage = "https://github.com/owner/package/";
            license = licenses.mit;
            maintainers = with maintainers; [ ];
            mainProgram = "package";
        };
    };
```
