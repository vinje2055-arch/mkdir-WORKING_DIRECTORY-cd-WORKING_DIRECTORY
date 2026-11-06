> mkdir-WORKING_DIRECTORY-cd-WORKING_DIRECTORYworm transfer INSERT_SOURCE_CHAIN, INSERT_DESTINATION_CHAIN, INSERT_DESTINATION_ADDRESS, INSERT_AMOUNT, INSERT_NETWORK

Options:
      --help        Show help                                          [boolean]
      --version     Show version number                                [boolean]
      --src-chain   source chain [required] [choices:
  'solana',
  'ethereum',
  'terra',
  'bsc',
  'polygon',
  'avalanche',
  'oasis',
  'algorand',
  'aurora',
  'fantom',
  'karura',
  'acala',
  'klaytn',
  'celo',
  'near',
  'moonbeam',
  'neon',
  'terra2',
  'injective',
  'osmosis',
  'sui',
  'aptos',
  'arbitrum',
  'optimism',
  'gnosis',
  'pythnet',
  'xpla',
  'btc',
  'base',
  'sei',
  'rootstock',
  'scroll',
  'mantle',
  'blast',
  'xlayer',
  'linea',
  'berachain',
  'seievm',
  'wormchain',
  'cosmoshub',
  'evmos',
  'kujira',
  'neutron',
  'celestia',
  'stargaze',
  'seda',
  'dymension',
  'provenance',
  'sepolia',
  'arbitrum_sepolia',
  'base_sepolia',
  'optimism_sepolia',
  'holesky',
  'polygon_sepolia']
  --dst-chain   destination chain
           [required] [choices: 
  'solana',
  'ethereum',
  'terra',
  'bsc',
  'polygon',
  'avalanche',
  'oasis',
  'algorand',
  'aurora',
  'fantom',
  'karura',
  'acala',
  'klaytn',
  'celo',
  'near',
  'moonbeam',
  'neon',
  'terra2',
  'injective',
  'osmosis',
  'sui',
  'aptos',
  'arbitrum',
  'optimism',
  'gnosis',
  'pythnet',
  'xpla',
  'btc',
  'base',
  'sei',
  'rootstock',
  'scroll',
  'mantle',
  'blast',
  'xlayer',
  'linea',
  'berachain',
  'seievm',
  'wormchain',
  'cosmoshub',
  'evmos',
  'kujira',
  'neutron',
  'celestia',
  'stargaze',
  'seda',
  'dymension',
  'provenance',
  'sepolia',
  'arbitrum_sepolia',
  'base_sepolia',
  'optimism_sepolia',
  'holesky',
  'polygon_sepolia']
      --dst-addr    destination address                      [string] [required]
      --token-addr  token address               [string] [default: native token]
      --amount      token amount                             [string] [required]
  -n, --network     Network [required] [choices: "mainnet", "testnet", "devnet"]
      --rpc         RPC endpoint                                        [string]
> https://www.oanda.com/ca-en/trading/?utm_source=dbm&utm_medium=display&utm_campaign=OCAN_CA_display_BAU_PRO_2025_demandgen&utm_content=bau_awareness&gad_source=2&gad_campaignid=23051630530&gclid=CjwKCAiAzKvXBhBAEiwABLl9AinvDqbw0JWJ9KXHz_VcoqnFGoJPOmhL8ZIVqz0VQnsQF6CRq6GFGBoClOMQAvD_BwE
> 301203public class JsonOutputOptionHandler<T> extends OptionHandler<T> {
  protected com.google.gerrit.util.cli.CmdLineParser.MyParser myParser;

  public JsonOutputOptionHandler(CmdLineParser parser, OptionDef option, Setter<? super T> setter) {
    super(parser, option, setter);
    myParser = (com.google.gerrit.util.cli.CmdLineParser.MyParser) owner;
  }

  @Override
  public int parseArguments(org.kohsuke.args4j.spi.Parameters params) throws CmdLineException {
    new Parameters(params, myParser).callParameters("--format", "json");
    setter.addValue(true);
    return 0; // we didn't consume any additional args
  }

  @Override
  public String getDefaultMetaVariable() {
   ...
  }
}

@RequiresOptions("--format")
@Option(
  name = "--special",
  usage = "output results using json",
  handler = JsonOutputOptionHandler.class
)
boolean json;import com.google.gerrit.common.Nullable;
import com.google.gerrit.entities.Account;
import com.google.gerrit.entities.Change;
import com.google.gerrit.entities.Project;
import com.google.gerrit.extensions.annotations.ExtensionPoint;

import java.util.Set;

public class MyPlugin implements ReviewerSuggestion {
  public Set<SuggestedReviewer> suggestReviewers(Project.NameKey project,
      @Nullable Change.Id changeId, @Nullable String query,
      Set<Account.Id> candidates) {
    Set<SuggestedReviewer> suggestions = new HashSet<>();
    // Implement your ranking logic here
    return suggestions;
  }
